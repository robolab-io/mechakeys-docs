<template>
	<main class="flex-1 select-none">
		<section id="support-page" class="py-[24px]" aria-label="Support section for MechaKeys">
			<Section class="">
				<div class="flex flex-col items-center justify-between">
					<!-- <h1 class="text-4xl sm:text-6xl font-extrabold tracking-tight flex items-center">Help Center
					</h1>
					<p class="mx-auto mt-6 max-w-2xl text-lg tracking-tight text-slate-300 text-center">We've got your back
						for all of your MechaKeys needs. Use the search box below to find what you need, or join us on <a
							class="text-[var(--colors-blue)]" href="https://discord.robolab.io" aria-label="github"
							target="_blank" rel="noopener">
							Discord
						</a> to chat.</p> -->
					<input class="genericTextInput max-w-2xl w-full sticky" type="text" v-model="searchQuery"
						placeholder="Search" />
				</div>

				<div v-if="filteredAccountHelp.topAnswer" class="mt-4 mb-16">
					<section class="mx-auto mt-8 text-2xl tracking-tight text-slate-300">Top Answer</section>
					<p class="mt-6 text-lg tracking-tight text-slate-300">Based on your search and number of matches</p>
					<div
						class="highlight-section mx-auto mt-6 mb-8 text-lg tracking-tight text-slate-300 p-8 bg-[var(--app-base2)] rounded-2xl border-solid border-[2px] border-[var(--borders-base2)]">
						<span class="text-slate-100 text-lg font-bold"
							v-html="highlightText(filteredAccountHelp.topAnswer.topic, 'topic')"></span>
						<div class="mt-4" v-html="highlightText(filteredAccountHelp.topAnswer.answer, 'answer')"></div>
					</div>

					<div v-if="filteredAccountHelp.topAnswer" class="w-full h-[2px] bg-[var(--borders-base3)] rounded-full mt-16"></div>
				</div>

				<div v-if="filteredAccountHelp.accountHelp.length > 0">
					<p class="mx-auto mt-8 text-2xl tracking-tight text-slate-300">My MechaKeys Account</p>

					<div
						class="highlight-section mx-auto mt-6 mb-8 text-lg tracking-tight text-slate-300 p-4 bg-[var(--app-base2)] rounded-2xl border-solid border-[2px] border-[var(--borders-base2)]">
						<details v-for="(h, i) in filteredAccountHelp.accountHelp" :key="'help-' + i" class="p-4"
							 :id="'accounthelp-' + i" :open="h.isExpanded">
							<summary class="cursor-pointer" @click="toggleExpansion(h)">
								<span class="ml-2 text-slate-100 text-lg font-bold"
									v-html="highlightText(h.topic, 'topic')"></span>
							</summary>
							<div class="mt-4 select-none leading-8 mb-4" v-html="highlightText(h.answer, 'answer')"></div>
							<!-- <a :href="'#accounthelp-' + i" class="px-4 py-2 bg-green-500 rounded-full select-none text-black z-10 text-sm font-bold pointer-events-auto" @click="handleAcctCopyLink(i)">Copy Link</a> -->
						</details>
					</div>
				</div>

				<div v-if="filteredAccountHelp.appHelp.length > 0">
					<p class="mx-auto mt-8 text-2xl tracking-tight text-slate-300">MechaKeys App</p>

					<div
						class="highlight-section mx-auto mt-6 mb-8 text-lg tracking-tight text-slate-300 p-4 bg-[var(--app-base2)] rounded-2xl border-solid border-[2px] border-[var(--borders-base2)]">
						<details v-for="(h, i) in filteredAccountHelp.appHelp" :key="'help-' + i" class="p-4"
							:id="'apphelp-' + i" :open="h.isExpanded">
							<summary class="cursor-pointer" @click="toggleExpansion(h)">
								<span class="ml-2 text-slate-100 text-lg font-bold"
									v-html="highlightText(h.topic, 'topic')"></span>
							</summary>
							<div class="mt-4 select-none leading-8 mb-4" v-html="highlightText(h.answer, 'answer')"></div>
							<!-- <a :href="'#apphelp-' + i" class="px-4 py-2 bg-green-500 rounded-full select-none text-black z-10 text-sm font-bold pointer-events-auto">Copy Link</a> -->
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

import { ref, computed, watch, onMounted } from 'vue';

const accountHelp = [
	{
		topic: 'I forgot my username',
		answer: `You can request to get your username to your registered account's email address. On the login screen, find the link called "Request Username" and follow the prompts, then check your email.`
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
	{
		topic: `I want to unlink my Discord account from my MechaKeys account`,
		answer: `Please note that MechaKeys developers are unable to unlink or relink accounts at this time. The only way to update what Discord account is linked is to create a new account.`
	}
];

const appHelp = [
	{
		topic: `What are the minimum requirements for MechaKeys?`,
		answer: `In general, you should make sure you have at least 200MB of storage on your PC to ensure MechaKeys is able to install soundpacks correctly. MechaKeys also requires about 250MB of RAM while you're using the UI. Closing the app to the tray will minimize resource usage.`
	},
	{
		topic: `What's the difference between "keystrokes" and "keycaps"?`,
		answer: `Keystrokes are the amount of times you click and type with MechaKeys open. Keycaps are the virtual currency you use to purchase new soundpacks, mousepacks, and avatars.`
	},
	{
		topic: `My keystrokes don't match the weekly leaderboard`,
		answer: `Leaderboard keystrokes are recorded during the week. If you had 100,000 keystrokes before the week started, and you get 50,000 more when a new leaderboard starts, only the 50,000 will be counted towards the leaderboard, not your lifetime total of 150,000. Please note that the leaderboard updates asynchronously from your actual sync times, meaning it may take up to an hour for your keystrokes to be reflected in the leaderboard's counts.`
	},
	{
		topic: `What are offlineStrokes?`,
		answer: `Please note that MechaKeys versions above 2.3.7 renamed this to "Invalid Keystrokes". offlineStrokes are keystrokes that are counted when you use the app while disconnected from the internet for an extended period of time, or when you deliberately disable syncing via Settings. offlineStrokes are not synced and do not count towards achievements.`
	},
	{
		topic: `What are deltaStrokes?`,
		answer: `Please note that MechaKeys versions above 2.3.7 renamed this to "Unsynced Keystrokes". deltaStrokes are keystrokes that have been counted but are not synced to MechaKeys' servers yet. This means they won't be reflected in the weekly leaderboard or the Discord bot until you sync them with our servers. You can sync your keystrokes using the Sync button in the topbar of the app.`
	},
	{
		topic: `I have x keystrokes, but I can't claim the achievement for it`,
		answer: `Please check the You page to see if you have offlineStrokes. You can refer to the help article above to learn what offlineStrokes are and why they don't count towards your achievement. Ensure that you have synced before trying to claim the achievement. If you're sure that you've synced but you're receiving and error while claiming, try again within 15 minutes.`
	},
	{
		topic: `How do I get XP on Discord?`,
		answer: `You can get XP by talking in the #general channel, as well as using certain commands like /daily and /pray. A lot of activity in the channel increases the amount of XP you get. There are also occasional minigames such as tumblebounce, which are hosted in #general by a staff member.`
	},
	{
		topic: `I have x XP on Discord, but I can't claim the achievement for it`,
		answer: `Ensure that you have synced before trying to claim the achievement. You can also try fully quitting and reopening MechaKeys.`
	},
	{
		topic: `I lost my purchases and need help recovering them`,
		answer: `Check to see if you're logged in to the correct account. Usernames are case sensitive, so be sure that you haven't logged in to an account with a different capitalization. Next, check your stats in Settings > Account to see if those match with what you believe. It's extremely rare for the stats to misalign with your account's actual stats, so join our <a
							class="text-[var(--colors-blue)]" href="https://discord.robolab.io" aria-label="github"
							target="_blank" rel="noopener">
							Discord
						</a> and send us your mecha.log and mecha.store files via Settings > Advanced. <span aria-hidden="true" class="!hidden">soundpack lost, keypack lost, mousepack lost</span>`
	},
	{
		topic: `I bought something, but I want a refund`,
		answer: `We don't support refunds at this time. For support with premium services and in-app content, please join our <a
							class="text-[var(--colors-blue)]" href="https://discord.robolab.io" aria-label="github"
							target="_blank" rel="noopener">
							Discord
						</a> and contact us.`
	},
	{
		topic: `MechaKeys is laggy and not responsive`,
		answer: `Try to refresh the app with CTRL + R. If the app still isn't responding, or nothing happens, <strong>close MechaKeys completely</strong>. Check your tray menu for the MechaKeys logo, right-click it, and click Quit, then reopen the app. Please check Settings > Experimental to see if the Real Time Wallpaper and Overlay settings are off. Make sure to try using MechaKeys with hardware acceleration disabled or enabled via Settings > Behavior. If all else fails, please join our <a
							class="text-[var(--colors-blue)]" href="https://discord.robolab.io" aria-label="github"
							target="_blank" rel="noopener">
							Discord
						</a> and create a help thread with your mecha.log file via Settings > Advanced. We would also appreciate a screenshot of MechaKeys' resource usage in your Task Manager (Windows).`
	},
	{
		topic: `MechaKeys is lagging my game or app`,
		answer: `Make sure your device isn't out of resources. Check your storage, memory usage, CPU, and GPU usage to see if there any other unaddressed issues in your system. As a minimum, MechaKeys requires about 200MB of storage to run properly, and at least 250MB of RAM. Try disabling hardware acceleration via Settings > Behavior to prevent MechaKeys from using your GPU to render its UI. If all else fails, please join our <a
							class="text-[var(--colors-blue)]" href="https://discord.robolab.io" aria-label="github"
							target="_blank" rel="noopener">
							Discord
						</a> and create a help thread with your mecha.log file via Settings > Advanced. We would also appreciate a screenshot of MechaKeys' resource usage in your Task Manager (Windows).`
	},
	{
		topic: `MechaKeys is making my mouse lag or stutter while using it`,
		answer: `We're aware of this specific issue and are actively looking into it. Please join our <a
							class="text-[var(--colors-blue)]" href="https://discord.robolab.io" aria-label="github"
							target="_blank" rel="noopener">
							Discord
						</a> and create a help thread with your mecha.log file via Settings > Advanced. We would also appreciate a screenshot of MechaKeys' resource usage in your Task Manager (Windows).`
	},
	{
		topic: `I can't hear MechaKeys while in game`,
		answer: `Quit MechaKeys fully, then try running MechaKeys as administrator (Windows). Find MechaKeys in your Start Menu, right-click, and select "Run As Administrator". This will allow us to listen to your keystrokes even when a game or app hijacks your keyboard in other manners.`
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

	const accountHelpResults = fuzzySearch(query, accountHelp);
	const appHelpResults = fuzzySearch(query, appHelp);

	const accountHelpMatches = accountHelpResults.topAnswer ? accountHelpResults.topAnswer.totalMatches : 0;
	const appHelpMatches = appHelpResults.topAnswer ? appHelpResults.topAnswer.totalMatches : 0;

	let topAnswer;
	if (accountHelpMatches > appHelpMatches) {
		topAnswer = accountHelpResults.topAnswer;
	} else if (appHelpMatches > 0) {
		topAnswer = appHelpResults.topAnswer;
	} else {
		topAnswer = null;
	}

	return {
		accountHelp: accountHelpResults.accountHelp,
		appHelp: appHelpResults.accountHelp,
		topAnswer
	};
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

async function handleAcctCopyLink (i) {
	await navigator.clipboard.writeText('https://v2.robolab.io/support#accounthelp-' + i);
}

onMounted(() => {
  if (window.location.hash) {
    const hash = window.location.hash.slice(1);
    const detailsElement = document.querySelector(`#${hash}`);
    
    if (detailsElement) {
      detailsElement.open = true;
    } else {
      // Check if the hash belongs to the accounthelp section
      const accountHelpDetails = document.querySelectorAll('[id^="accounthelp"]');
      accountHelpDetails.forEach((element) => {
        if (element.id === hash) {
          element.open = true;
        }
      });
    }
  }
});

</script>

<style>
.highlighted {
	background-color: var(--colors-yellow);
	color: black;
	text-shadow: 0 0 2px hsla(0, 0, 0, 0.9);
}

.highlight-section:hover > * > span, .highlight-section:hover > details > summary > span > span, .highlight-section:hover > details > div > *, .highlight-section:hover > details > div > * > * {
	transition: 0.2s ease;
	background-color: revert !important;
	color: revert !important;
}

details:focus, summary:focus, details:active, summary:active {
	outline: none;
	border: 0px solid transparent;
}
</style>
