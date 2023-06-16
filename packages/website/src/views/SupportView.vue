<template>
	<main class="flex-1">
		<section id="support-page" class="py-20 sm:py-[48px]" aria-label="Support section for MechaKeys">
			<Section class="">
				<div class="flex flex-col items-center justify-between">
					<h1 class="text-4xl sm:text-6xl font-extrabold tracking-tight sm:text-3xl flex items-center">Help Center
					</h1>
					<p class="mx-auto mt-6 max-w-2xl text-lg tracking-tight text-slate-300 text-center">We've got your back
						for all of your MechaKeys needs. Use the search box below to find what you need, or join us on <a
							class="text-[var(--colors-blue)]" href="https://discord.robolab.io" aria-label="github"
							target="_blank" rel="noopener">
							Discord
						</a> to chat.</p>
					<input class="genericTextInput mt-8 max-w-2xl w-full" type="text" v-model="searchQuery"
						placeholder="Search" />
				</div>

				<div v-if="filteredAccountHelp.topAnswer" class="mt-4">
					<section class="mx-auto mt-16 text-2xl tracking-tight text-slate-300">Top Answer</section>

					<div
						class="mx-auto mt-6 mb-8 text-lg tracking-tight text-slate-300 p-4 bg-[var(--app-base2)] rounded-2xl border-solid border-[1px] border-[var(--borders-base1)]">
						<details class="p-4" open>
							<summary class="select-none cursor-pointer"
								@click="toggleExpansion(filteredAccountHelp.topAnswer)">
								<span class="ml-2 text-slate-100 text-lg font-bold"
									v-html="highlightText(filteredAccountHelp.topAnswer.topic, 'topic')"></span>
							</summary>
							<div class="mt-4 select-none"
								v-html="highlightText(filteredAccountHelp.topAnswer.answer, 'answer')"></div>
						</details>
					</div>
				</div>

				<div v-if="filteredAccountHelp.accountHelp.length > 0">
					<p class="mx-auto mt-16 text-2xl tracking-tight text-slate-300">Account Issues</p>

					<div
						class="mx-auto mt-6 mb-8 text-lg tracking-tight text-slate-300 p-4 bg-[var(--app-base2)] rounded-2xl border-solid border-[1px] border-[var(--borders-base1)]">
						<details v-for="(h, i) in filteredAccountHelp.accountHelp" :key="'help-' + i" class="p-4"
							:open="h.isExpanded">
							<summary class="select-none cursor-pointer" @click="toggleExpansion(h)">
								<span class="ml-2 text-slate-100 text-lg font-bold"
									v-html="highlightText(h.topic, 'topic')"></span>
							</summary>
							<div class="mt-4 select-none" v-html="highlightText(h.answer, 'answer')"></div>
						</details>
					</div>
				</div>

				<div v-if="filteredAccountHelp.appHelp.length > 0">
					<p class="mx-auto mt-16 text-2xl tracking-tight text-slate-300">App Issues</p>

					<div
						class="mx-auto mt-6 mb-8 text-lg tracking-tight text-slate-300 p-4 bg-[var(--app-base2)] rounded-2xl border-solid border-[1px] border-[var(--borders-base1)]">
						<details v-for="(h, i) in filteredAccountHelp.appHelp" :key="'help-' + i" class="p-4"
							:open="h.isExpanded">
							<summary class="select-none cursor-pointer" @click="toggleExpansion(h)">
								<span class="ml-2 text-slate-100 text-lg font-bold"
									v-html="highlightText(h.topic, 'topic')"></span>
							</summary>
							<div class="mt-4 select-none" v-html="highlightText(h.answer, 'answer')"></div>
						</details>
					</div>
				</div>

				<div v-if="filteredAccountHelp.appHelp.length === 0 && filteredAccountHelp.accountHelp.length === 0"
					class="mt-4">
					We couldn't find what you're looking for. Try narrowing your search or look through the headings to find
					a specific category.
				</div>
			</Section>
		</section>
	</main>
</template>
  

<script setup>
import Section from '@/components/LandingSection.vue';

import { ref, computed, watch } from 'vue';

const accountHelp = [
	{
		topic: 'I forgot my username',
		answer: `
					You can request to get your username to your registered account's email address. On the login screen, find the link called "Request Username" and follow the prompts, then check your email.
					`
	},
	{
		topic: 'I forgot my password',
		answer: `You can request to reset your password. On the login screen, find the link called "Reset Password" and follow the prompts. You'll be asked for your username, and we'll send you an email for confirmation. Copy the code in the confirmation email, enter the reset code in the prompt, and set a new password.`
	},
	{
		topic: 'I forgot my email',
		answer: `Please note that MechaKeys developers are unable to help with lost, inactive, or hacked emails. You can see what email you registered to MechaKeys with via Settings > Account and check your email there.`
	},
	{
		topic: 'I need to change my email',
		answer: 'Please note that MechaKeys developers are unable to change your account\'s email. The only way to update your email is to create a new account at this time.'
	},
	{
		topic: 'I want to change my username',
		answer: `We don't support changing your username at this time.`
	},
];

const appHelp = [
	{
		topic: `I lost my purchases and need help recovering them`,
		answer: ``
	},
	{
		topic: `I bought something, but I want a refund`,
		answer: ``
	},
	{
		topic: `MechaKeys is laggy and not responsive`,
		answer: ``
	},
	{
		topic: `MechaKeys is lagging my game or app`,
		answer: ``
	},
	{
		topic: `MechaKeys is making my mouse lag or stutter while using it`,
		answer: ``
	},
	{
		topic: `I can't hear MechaKeys while in game`,
		answer: ``
	},
	{
		topic: ``,
		answer: ``
	},
];

const searchQuery = ref('');

function fuzzySearch(query, items) {
	const filteredItems = items.map(item => {
		const topicMatches = countMatches(item.topic, query);
		const answerMatches = countMatches(item.answer, query);
		const totalMatches = topicMatches + answerMatches;

		return {
			...item,
			isExpanded: false,
			topicMatches,
			answerMatches,
			totalMatches
		};
	}).filter(item => item.topicMatches > 0 || item.answerMatches > 0);

	const sortedItems = filteredItems.sort((a, b) => b.totalMatches - a.totalMatches);
	const topAnswer = sortedItems.length > 0 ? sortedItems[0] : null;

	return {
		accountHelp: sortedItems,
		appHelp: sortedItems.filter(item => appHelp.includes(item)),
		topAnswer: topAnswer && topAnswer.totalMatches > 0 ? topAnswer : null
	};
}

function countMatches(str, query) {
	const queryWords = query.toLowerCase().split(' ');
	let count = 0;

	for (const word of queryWords) {
		if (str.toLowerCase().includes(word)) {
			count++;
		}
	}

	return count;
}

const filteredAccountHelp = computed(() => {
	const query = searchQuery.value.toLowerCase().trim();

	if (query === '') {
		return {
			accountHelp: accountHelp.map(item => ({ ...item, isExpanded: false })),
			appHelp: appHelp.map(item => ({ ...item, isExpanded: false })),
			topAnswer: null
		};
	}

	return fuzzySearch(query, [...accountHelp, ...appHelp]);
});

const highlightText = (text, field) => {
	const query = searchQuery.value.toLowerCase().trim();

	if (query === '') {
		return text;
	}

	const keywords = query.split(' ');
	const regex = new RegExp(keywords.join('|'), 'gi');

	if (field === 'topic' || field === 'answer') {
		return text.replace(regex, (match) => `<span class="highlighted">${match}</span>`);
	}

	return text;
};

const toggleExpansion = (item) => {
	if (searchQuery.value !== '') {
		item.isExpanded = true;
	} else {
		item.isExpanded = !item.isExpanded;
	}
};

watch(searchQuery, (newValue) => {
	const isExpanded = newValue !== '';

	filteredAccountHelp.value.accountHelp.forEach((item) => {
		item.isExpanded = isExpanded;
	});

	filteredAccountHelp.value.appHelp.forEach((item) => {
		item.isExpanded = isExpanded;
	});
});
</script>

<style>
.highlighted {
	background-color: var(--colors-yellow50);
	color: white;
}</style>