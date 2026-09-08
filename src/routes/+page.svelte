<script lang="ts">
	// Icons
	const icons = {
		logo: `<svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg" class="w-6 h-6 text-blue-500"><path d="M12 2L14.5 9H22L16 13.5L18.5 21L12 16.5L5.5 21L8 13.5L2 9H9.5L12 2Z" fill="currentColor" stroke="currentColor" stroke-width="2" stroke-linejoin="round"/></svg>`, // Placeholder for flower
		clock: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><circle cx="12" cy="12" r="10"/><polyline points="12 6 12 12 16 14"/></svg>`,
		arrowRight: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><line x1="5" y1="12" x2="19" y2="12"/><polyline points="12 5 19 12 12 19"/></svg>`,
		reflection: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><path d="M2 3h6a4 4 0 0 1 4 4v14a3 3 0 0 0-3-3H2z"/><path d="M22 3h-6a4 4 0 0 0-4 4v14a3 3 0 0 1 3-3h7z"/></svg>`,
		productivity: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><polygon points="13 2 3 14 12 14 11 22 21 10 12 10 13 2"/></svg>`,
		memory: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><path d="M9.5 2A2.5 2.5 0 0 1 12 4.5v15a2.5 2.5 0 0 1-4.96.44 2.5 2.5 0 0 1-2.96-3.08 3 3 0 0 1-.34-5.58 2.5 2.5 0 0 1 1.32-4.24 2.5 2.5 0 0 1 1.98-3A2.5 2.5 0 0 1 9.5 2Z"/><path d="M14.5 2A2.5 2.5 0 0 0 12 4.5v15a2.5 2.5 0 0 0 4.96.44 2.5 2.5 0 0 0 2.96-3.08 3 3 0 0 0 .34-5.58 2.5 2.5 0 0 0-1.32-4.24 2.5 2.5 0 0 0-1.98-3A2.5 2.5 0 0 0 14.5 2Z"/></svg>`,
		clarity: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><path d="M12 2v4"/><path d="M12 18v4"/><path d="M4.93 4.93l2.83 2.83"/><path d="M16.24 16.24l2.83 2.83"/><path d="M2 12h4"/><path d="M18 12h4"/><path d="M4.93 19.07l2.83-2.83"/><path d="M16.24 7.76l2.83-2.83"/></svg>`,
		speedometer: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-5 h-5"><path d="M22 12A10 10 0 0 0 12 2v10z"/></svg>`, // Simplified
		shield: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-5 h-5"><path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"/></svg>`,
		sparkles: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-5 h-5"><path d="m12 3-1.912 5.813a2 2 0 0 1-1.275 1.275L3 12l5.813 1.912a2 2 0 0 1 1.275 1.275L12 21l1.912-5.813a2 2 0 0 1 1.275-1.275L21 12l-5.813-1.912a2 2 0 0 1-1.275-1.275L12 3Z"/></svg>`,
		soundwave: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-5 h-5"><path d="M12 2v20"/><path d="M16 6v12"/><path d="M20 10v4"/><path d="M8 6v12"/><path d="M4 10v4"/></svg>`,
		plus: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-5 h-5"><line x1="12" y1="5" x2="12" y2="19"/><line x1="5" y1="12" x2="19" y2="12"/></svg>`,
		check: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><polyline points="20 6 9 17 4 12"/></svg>`,
		calendar: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><rect x="3" y="4" width="18" height="18" rx="2" ry="2"/><line x1="16" y1="2" x2="16" y2="6"/><line x1="8" y1="2" x2="8" y2="6"/><line x1="3" y1="10" x2="21" y2="10"/></svg>`,
		repeat: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><polyline points="17 1 21 5 17 9"/><path d="M3 11V9a4 4 0 0 1 4-4h14"/><polyline points="7 23 3 19 7 15"/><path d="M21 13v2a4 4 0 0 1-4 4H3"/></svg>`,
		search: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><circle cx="11" cy="11" r="8"/><line x1="21" y1="21" x2="16.65" y2="16.65"/></svg>`,
		camera: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><path d="M23 19a2 2 0 0 1-2 2H3a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h4l2-3h6l2 3h4a2 2 0 0 1 2 2z"/><circle cx="12" cy="13" r="4"/></svg>`,
		mic: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><path d="M12 1a3 3 0 0 0-3 3v8a3 3 0 0 0 6 0V4a3 3 0 0 0-3-3z"/><path d="M19 10v2a7 7 0 0 1-14 0v-2"/><line x1="12" y1="19" x2="12" y2="23"/><line x1="8" y1="23" x2="16" y2="23"/></svg>`,
		download: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><path d="M21 15v4a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2v-4"/><polyline points="7 10 12 15 17 10"/><line x1="12" y1="15" x2="12" y2="3"/></svg>`,
		layout: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><rect x="3" y="3" width="18" height="18" rx="2" ry="2"/><line x1="3" y1="9" x2="21" y2="9"/><line x1="9" y1="21" x2="9" y2="9"/></svg>`,
		target: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><circle cx="12" cy="12" r="10"/><circle cx="12" cy="12" r="6"/><circle cx="12" cy="12" r="2"/></svg>`,
		list: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><line x1="8" y1="6" x2="21" y2="6"/><line x1="8" y1="12" x2="21" y2="12"/><line x1="8" y1="18" x2="21" y2="18"/><line x1="3" y1="6" x2="3.01" y2="6"/><line x1="3" y1="12" x2="3.01" y2="12"/><line x1="3" y1="18" x2="3.01" y2="18"/></svg>`,
		link: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"/><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"/></svg>`,
		maximize: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><path d="M8 3H5a2 2 0 0 0-2 2v3m18 0V5a2 2 0 0 0-2-2h-3m0 18h3a2 2 0 0 0 2-2v-3M3 16v3a2 2 0 0 0 2 2h3"/></svg>`,
		externalLink: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><path d="M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6"/><polyline points="15 3 21 3 21 9"/><line x1="10" y1="14" x2="21" y2="3"/></svg>`,
	};
</script>

<div class="min-h-screen bg-white">
	<!-- Header -->
	<header class="flex items-center justify-between px-6 py-4 max-w-7xl mx-auto">
		<div class="flex items-center gap-2">
			<!-- Logo Icon -->
			<div class="text-blue-600">
				<svg viewBox="0 0 24 24" fill="currentColor" class="w-6 h-6">
					<path d="M12 2C13.1 2 14 2.9 14 4C14 5.1 13.1 6 12 6C10.9 6 10 5.1 10 4C10 2.9 10.9 2 12 2ZM12 22C10.9 22 10 21.1 10 20C10 18.9 10.9 18 12 18C13.1 18 14 18.9 14 20C14 21.1 13.1 22 12 22ZM6 12C6 10.9 5.1 10 4 10C2.9 10 2 10.9 2 12C2 13.1 2.9 14 4 14C5.1 14 6 13.1 6 12ZM22 12C22 13.1 21.1 14 20 14C18.9 14 18 13.1 18 12C18 10.9 18.9 10 20 10C21.1 10 22 10.9 22 12ZM17.66 7.34C18.44 6.56 19.7 6.56 20.48 7.34C21.26 8.12 21.26 9.38 20.48 10.16C19.7 10.94 18.44 10.94 17.66 10.16C16.88 9.38 16.88 8.12 17.66 7.34ZM6.34 16.66C5.56 17.44 4.3 17.44 3.52 16.66C2.74 15.88 2.74 14.62 3.52 13.84C4.3 13.06 5.56 13.06 6.34 13.84C7.12 14.62 7.12 15.88 6.34 16.66ZM16.66 17.66C15.88 18.44 15.88 19.7 16.66 20.48C17.44 21.26 18.7 21.26 19.48 20.48C20.26 19.7 20.26 18.44 19.48 17.66C18.7 16.88 18.7 15.62 17.92 14.84L16.66 17.66ZM7.34 6.34C8.12 5.56 8.12 4.3 7.34 3.52C6.56 2.74 5.3 2.74 4.52 3.52C3.74 4.3 3.74 5.56 4.52 6.34C5.3 7.12 6.56 7.12 7.34 6.34Z" />
					<circle cx="12" cy="12" r="3" class="text-blue-500" />
				</svg>
			</div>
			<span class="font-bold text-xl tracking-tight">Finakets</span>
		</div>
		<nav class="flex items-center gap-6 text-sm font-medium">
			<a href="#" class="text-gray-600 hover:text-gray-900">Guide</a>
			<a href="#" class="bg-gray-100 px-4 py-2 rounded-lg text-gray-900 hover:bg-gray-200 transition-colors">Login</a>
		</nav>
	</header>

	<main>
		<!-- Hero Section -->
		<section class="max-w-4xl mx-auto px-6 pt-12 pb-20 text-center">
			<div class="inline-flex items-center gap-2 text-gray-500 text-sm mb-6">
				{@html icons.clock}
				<span>For macOS & iOS</span>
			</div>
			
			<h1 class="text-5xl md:text-6xl font-bold tracking-tight text-gray-900 mb-6 leading-[1.1]">
				Capture once. Finakets forever.
			</h1>
			
			<p class="text-xl text-gray-600 mb-10 max-w-2xl mx-auto">
				The insight-to-action loop for people who think for a living.
			</p>

			<div class="flex flex-col sm:flex-row items-center justify-center gap-4 max-w-lg mx-auto mb-16">
				<div class="relative w-full">
					<input 
						type="email" 
						placeholder="Your email address" 
						class="w-full pl-4 pr-12 py-3 rounded-xl border border-gray-200 focus:outline-none focus:ring-2 focus:ring-blue-500/20 focus:border-blue-500 transition-all"
					/>
					<button class="absolute right-2 top-1/2 -translate-y-1/2 p-1.5 text-gray-400 hover:text-gray-600">
						{@html icons.arrowRight}
					</button>
				</div>
				<div class="text-xs text-left text-gray-500 w-full sm:w-auto shrink-0">
					Request an invitation,<br>Finakets is in limited access.
				</div>
			</div>

			<!-- App Screenshot Placeholder -->
			<div class="relative rounded-2xl border border-gray-200 shadow-2xl bg-white overflow-hidden aspect-[16/10] mb-12 group">
				<!-- This represents the complex app interface -->
				<div class="absolute inset-0 bg-gray-50 flex">
					<!-- Sidebar -->
					<div class="w-64 border-r border-gray-200 bg-white p-4 hidden md:flex flex-col gap-4">
						<div class="h-8 w-full bg-gray-100 rounded animate-pulse"></div>
						<div class="space-y-2">
							<div class="h-4 w-3/4 bg-gray-100 rounded"></div>
							<div class="h-4 w-1/2 bg-gray-100 rounded"></div>
							<div class="h-4 w-5/6 bg-gray-100 rounded"></div>
						</div>
					</div>
					<!-- Main Content -->
					<div class="flex-1 p-6">
						<div class="h-8 w-1/3 bg-gray-100 rounded mb-6"></div>
						<div class="space-y-4">
							<div class="h-32 w-full bg-white border border-gray-200 rounded-xl p-4 shadow-sm">
								<div class="flex gap-3 mb-3">
									<div class="w-8 h-8 rounded-full bg-gray-200"></div>
									<div class="space-y-1">
										<div class="h-3 w-24 bg-gray-200 rounded"></div>
										<div class="h-3 w-16 bg-gray-100 rounded"></div>
									</div>
								</div>
								<div class="h-2 w-full bg-gray-100 rounded mb-2"></div>
								<div class="h-2 w-5/6 bg-gray-100 rounded"></div>
							</div>
							<div class="h-32 w-full bg-white border border-gray-200 rounded-xl p-4 shadow-sm"></div>
						</div>
					</div>
				</div>
				
				<!-- Overlay text to indicate it's a screenshot -->
				<div class="absolute inset-0 flex items-center justify-center bg-black/5 opacity-0 group-hover:opacity-100 transition-opacity pointer-events-none">
					<span class="bg-white px-4 py-2 rounded-full shadow-sm text-sm font-medium">App Interface</span>
				</div>
			</div>

			<!-- Bottom Icons -->
			<div class="flex flex-wrap justify-center gap-8 md:gap-12 text-sm font-medium text-gray-700">
				<div class="flex items-center gap-2">
					{@html icons.reflection}
					<span>For reflection</span>
				</div>
				<div class="flex items-center gap-2">
					{@html icons.productivity}
					<span>For productivity</span>
				</div>
				<div class="flex items-center gap-2">
					{@html icons.memory}
					<span>For memory</span>
				</div>
				<div class="flex items-center gap-2">
					{@html icons.clarity}
					<span>For clarity</span>
				</div>
			</div>
		<!-- Features Grid -->
		<section class="max-w-6xl mx-auto px-6 py-20">
			<h2 class="text-3xl md:text-4xl font-bold text-gray-900 mb-12 max-w-lg leading-tight">
				Comprehensive, institutional-grade thinking tools for investors and traders.
			</h2>

			<div class="grid grid-cols-1 md:grid-cols-3 gap-6">
				<!-- Card 1 -->
				<div class="bg-gray-50 p-8 rounded-2xl flex flex-col items-start h-64">
					<div class="mb-auto text-gray-900">
						{@html icons.speedometer}
					</div>
					<div>
						<h3 class="font-bold text-lg mb-2 text-gray-900">Optimized for rapid thought</h3>
						<p class="text-sm text-gray-600 leading-relaxed">All of your investment workflows, fast and smooth, built for seamless focus.</p>
					</div>
				</div>

				<!-- Card 2 -->
				<div class="bg-gray-50 p-8 rounded-2xl flex flex-col items-start h-64">
					<div class="mb-auto text-gray-900">
						{@html icons.shield}
					</div>
					<div>
						<h3 class="font-bold text-lg mb-2 text-gray-900">Privacy and security built in</h3>
						<p class="text-sm text-gray-600 leading-relaxed">Your strategies and data stay confidential—local-first, encrypted end-to-end sync.</p>
					</div>
				</div>

				<!-- Card 3 -->
				<div class="bg-gray-50 p-8 rounded-2xl flex flex-col items-start h-64">
					<div class="mb-auto text-gray-900">
						{@html icons.sparkles}
					</div>
					<div>
						<h3 class="font-bold text-lg mb-2 text-gray-900">Decision agents powered by AI</h3>
						<p class="text-sm text-gray-600 leading-relaxed">Structured, self-learning artificial intelligence utilizes institutional methods to sharpen your edge.</p>
					</div>
				</div>

				<!-- Card 4 -->
				<div class="bg-gray-50 p-8 rounded-2xl flex flex-col items-start h-64">
					<div class="mb-auto text-gray-900">
						{@html icons.soundwave}
					</div>
					<div>
						<h3 class="font-bold text-lg mb-2 text-gray-900">Voice capture for fast journaling</h3>
						<p class="text-sm text-gray-600 leading-relaxed">Record investment theses or market briefings straight into your process.</p>
					</div>
				</div>

				<!-- Card 5 -->
				<div class="bg-gray-50 p-8 rounded-2xl flex flex-col items-start h-64">
					<div class="mb-auto text-gray-900">
						{@html icons.plus}
					</div>
					<div>
						<h3 class="font-bold text-lg mb-2 text-gray-900">Capture every market insight</h3>
						<p class="text-sm text-gray-600 leading-relaxed">Attach news, charts, links, screenshots, and notes—every input to your decision process, in one place.</p>
					</div>
				</div>
			</div>
		</section>

		<!-- Think Tank Section -->
		<section class="max-w-6xl mx-auto px-6 py-20">
			<div class="mb-16">
				<span class="inline-block bg-purple-100 text-purple-700 px-3 py-1 rounded-full text-xs font-semibold uppercase tracking-wide mb-6">
					With best-in-class AI
				</span>
				<h2 class="text-4xl md:text-5xl font-bold text-purple-900 mb-6 tracking-tight">
					A Socratic engine for decision-making
				</h2>
				<p class="text-xl text-gray-600 max-w-2xl leading-relaxed">
					Finakets guides your thinking with institutional frameworks, turning scattered insights into rigorous decisions, no analyst team required.
				</p>
			</div>

			<div class="bg-purple-50 rounded-3xl p-8 md:p-12 mb-16">
				<div class="grid grid-cols-1 md:grid-cols-2 gap-8 mb-8">
					<!-- Left Visual: Nova Agent -->
					<div class="relative bg-white rounded-2xl shadow-lg p-6 overflow-hidden min-h-[300px]">
						<div class="absolute top-0 left-0 w-full h-1 bg-gradient-to-r from-purple-500 to-pink-500"></div>
						<div class="flex items-center gap-3 mb-6">
							<div class="w-10 h-10 rounded-full bg-gradient-to-br from-purple-600 to-orange-400 flex items-center justify-center text-white font-bold text-xs">
								N
							</div>
							<div>
								<div class="font-bold text-gray-900">Nova</div>
								<div class="text-xs text-purple-600 font-medium uppercase tracking-wider">The Playful Explorer</div>
							</div>
						</div>
						<div class="space-y-4 text-sm">
							<div class="bg-purple-50 p-4 rounded-xl rounded-tl-none text-gray-800">
								I experiment with every market puzzle, probing 'why' and 'what if' on every trade, helping you look at your investments sideways and sharpen your reasoning.
							</div>
							<div class="flex gap-2">
								<span class="bg-purple-900 text-white px-3 py-1 rounded-full text-xs font-medium">Analytical</span>
								<span class="bg-purple-900 text-white px-3 py-1 rounded-full text-xs font-medium">Exploratory</span>
							</div>
							<div class="flex gap-2">
								<span class="bg-purple-900 text-white px-3 py-1 rounded-full text-xs font-medium">Objective</span>
								<span class="bg-purple-900 text-white px-3 py-1 rounded-full text-xs font-medium">Socratic</span>
							</div>
						</div>
						<div class="mt-6">
							<button class="w-full py-2 border border-purple-200 text-purple-700 font-medium rounded-lg hover:bg-purple-50 transition-colors">
								Add to workspace
							</button>
						</div>
					</div>

					<!-- Right Visual: Chat Interface -->
					<div class="bg-white rounded-2xl shadow-lg p-6 min-h-[300px] flex flex-col">
						<div class="flex items-center gap-2 mb-4 text-xs text-gray-400 border-b border-gray-100 pb-2 overflow-hidden whitespace-nowrap">
							<div class="w-2 h-2 rounded-full bg-gray-300"></div>
							<span>https://marketinsight.tradersedge.com/notes/socratic-trading</span>
						</div>
						<div class="flex-1 space-y-4">
							<div class="border border-gray-100 rounded-lg p-4">
								<h4 class="font-bold text-gray-900 text-sm mb-1">Framework: Socratic Trading Logs</h4>
								<div class="text-xs text-gray-500 mb-2">marketinsight.tradersedge.com</div>
								<p class="text-xs text-gray-600 line-clamp-3">
									Discover how institutional desks use structured questioning and decision journaling to outperform luck—turning mental models into repeatable edges.
								</p>
							</div>
							<div class="flex gap-2 items-center text-xs text-gray-500">
								<div class="flex -space-x-2">
									<div class="w-6 h-6 rounded-full bg-gray-200 border-2 border-white"></div>
									<div class="w-6 h-6 rounded-full bg-gray-300 border-2 border-white"></div>
								</div>
								<span>Research and Playbook</span>
							</div>
							<div class="space-y-3 pt-2">
								<div class="flex gap-3">
									<div class="w-6 h-6 rounded-full bg-gray-800 shrink-0"></div>
									<div class="text-xs text-gray-800">
										<p class="font-bold mb-1">Summarize best practices for P&L journaling</p>
									</div>
								</div>
								<div class="flex gap-3">
									<div class="w-6 h-6 rounded-full bg-teal-500 shrink-0"></div>
									<div class="text-xs text-gray-600 bg-gray-50 p-3 rounded-lg rounded-tl-none">
										<p>Use explicit reasoning, timestamp every decision, run regular reviews, and link supporting evidence for every major trade.</p>
									</div>
								</div>
							</div>
						</div>
					</div>
				</div>

				<!-- Bottom Visual: Input Processing -->
				<div class="bg-white rounded-2xl shadow-lg p-6 md:p-8">
					<div class="relative mb-8">
						<input type="text" value="What market question are you exploring?" class="w-full bg-gray-50 border-none rounded-xl py-4 pl-12 pr-4 text-gray-500 focus:ring-0" readonly />
						<div class="absolute left-4 top-1/2 -translate-y-1/2 text-gray-400">
							{@html icons.camera}
						</div>
						<div class="absolute right-4 top-1/2 -translate-y-1/2 flex gap-2 text-gray-400">
							{@html icons.mic}
							{@html icons.download}
						</div>
					</div>

					<div class="flex justify-center mb-8">
						<span class="bg-gray-100 text-gray-500 text-xs px-3 py-1 rounded-full">AI model update: new market-tailored engine released!</span>
					</div>

					<div class="bg-purple-50/50 rounded-xl p-6 border border-purple-100">
						<div class="space-y-3">
							<div class="flex items-center gap-3">
								<div class="w-3 h-3 rounded-full bg-pink-500 animate-pulse"></div>
								<span class="text-sm text-gray-700">Nova is assessing market context</span>
							</div>
							<div class="flex items-start gap-3">
								<div class="w-3 h-3 rounded-full bg-green-500 mt-1"></div>
								<div class="text-sm text-gray-700">
									<span class="font-medium">Nova is reviewing</span> 
									<span class="font-bold bg-white px-1 rounded border border-gray-200 mx-1">72 recent positions</span> 
									and checking 
									<span class="font-bold bg-white px-1 rounded border border-gray-200 mx-1">5 playbooks</span> 
									for historical relevance.
									<p class="text-xs text-gray-500 mt-1 max-w-md">Found key mentions around risk management in your log. Finakets uses AI to spot emerging patterns and update your process.</p>
								</div>
							</div>
							<div class="flex items-center gap-3">
								<div class="w-3 h-3 rounded-full bg-green-500"></div>
								<span class="text-sm text-gray-700">Tagged entry in <span class="bg-purple-500 text-white px-2 py-0.5 rounded text-xs font-bold">strategy notes</span></span>
							</div>
							<div class="flex items-center gap-3">
								<div class="w-3 h-3 rounded-full border-2 border-gray-300 border-t-gray-500 animate-spin"></div>
								<span class="text-sm text-gray-500">Researching the web for <span class="text-blue-500">hedge fund process best practices</span></span>
							</div>
						</div>
					</div>
				</div>
			</div>

			<div class="grid grid-cols-1 md:grid-cols-2 gap-x-12 gap-y-4 max-w-4xl">
				<p class="text-xl text-gray-600 mb-6 md:col-span-2 leading-relaxed">
					Your AI agents never sleep—detecting signals, monitoring lists, mapping your moves in real time so your strategy stays on edge.
				</p>
				
				<div class="space-y-4">
					<div class="flex items-center gap-3 text-purple-800 font-medium">
						{@html icons.sparkles}
						<span>Decision agents challenge your logic</span>
					</div>
					<div class="flex items-center gap-3 text-purple-800 font-medium">
						{@html icons.target}
						<span>Keep you anchored to your investment goals</span>
					</div>
					<div class="flex items-center gap-3 text-purple-800 font-medium">
						{@html icons.plus}
						<span>Auto-organize by strategy</span>
					</div>
				</div>

				<div class="space-y-4">
					<div class="flex items-center gap-3 text-purple-800 font-medium">
						{@html icons.layout}
						<span>Connect related trades and signals</span>
					</div>
					<div class="flex items-center gap-3 text-purple-800 font-medium">
						{@html icons.maximize}
						<span>Summarize key market links</span>
					</div>
					<div class="flex items-center gap-3 text-purple-800 font-medium">
						{@html icons.externalLink}
						<span>Integrate screenshots as evidence</span>
					</div>
				</div>
			</div>
		</section>

		<!-- Insights to Action Section -->
		<section class="max-w-6xl mx-auto px-6 py-20">
			<div class="mb-16">
				<span class="inline-block bg-orange-100 text-orange-700 px-3 py-1 rounded-full text-xs font-semibold uppercase tracking-wide mb-6">
					Planner
				</span>
				<h2 class="text-4xl md:text-5xl font-bold text-orange-900 mb-6 tracking-tight">
					From insights to execution
				</h2>
				<p class="text-xl text-gray-600 max-w-2xl leading-relaxed">
					Decision agents decompose complex plans, manage trade logs, and track your progress.
				</p>
			</div>

			<div class="bg-orange-50 rounded-3xl p-8 md:p-12 mb-16">
				<div class="bg-white rounded-2xl shadow-sm p-6 md:p-8 max-w-3xl mx-auto">
					<!-- Stats -->
					<div class="grid grid-cols-4 gap-4 mb-8">
						<div class="bg-green-100 p-3 rounded-xl">
							<div class="text-xs font-bold text-green-800 mb-1">Today</div>
							<div class="text-2xl font-bold text-green-900">3</div>
						</div>
						<div class="bg-orange-100 p-3 rounded-xl">
							<div class="text-xs font-bold text-orange-800 mb-1">Upcoming</div>
							<div class="text-2xl font-bold text-orange-900">19</div>
						</div>
						<div class="bg-gray-100 p-3 rounded-xl">
							<div class="text-xs font-bold text-gray-600 mb-1">All Tasks</div>
							<div class="text-2xl font-bold text-gray-900">22</div>
						</div>
						<div class="bg-gray-100 p-3 rounded-xl">
							<div class="text-xs font-bold text-gray-600 mb-1">Completed</div>
							<div class="text-2xl font-bold text-gray-900">6</div>
						</div>
					</div>

					<!-- Task List -->
					<div class="space-y-6">
						<div>
							<div class="text-xs font-bold text-red-500 mb-2 tracking-wide">OVERDUE</div>
							<div class="flex gap-4 items-start group">
								<div class="mt-1 w-5 h-5 rounded-full border-2 border-red-500 flex items-center justify-center cursor-pointer"></div>
								<div class="flex-1">
									<h4 class="font-bold text-gray-900">Update options strategy deck</h4>
									<p class="text-xs text-gray-500 mt-1">Review and finalize next quarter's risk scenarios in the playbook.</p>
									<div class="text-xs text-red-500 mt-1 font-medium">YESTERDAY · 2:00 PM</div>
								</div>
							</div>
						</div>

						<div>
							<div class="text-xs font-bold text-red-500 mb-2 tracking-wide">TODAY</div>
							<div class="flex gap-4 items-start group">
								<div class="mt-1 w-5 h-5 rounded-full border-2 border-gray-300 group-hover:border-gray-400 cursor-pointer"></div>
								<div class="flex-1">
									<h4 class="font-bold text-gray-900">Execute capital allocation review</h4>
									<p class="text-xs text-gray-500 mt-1">Walk through this month’s allocation, verifying adherence to portfolio strategy.</p>
									<div class="flex gap-2 text-xs text-gray-400 mt-1">
										<span>TODAY · 08:00 AM</span>
										<span>•</span>
										<span class="flex items-center gap-1">{@html icons.repeat} REPEATS MONTHLY</span>
									</div>
								</div>
							</div>
						</div>

						<div>
							<div class="flex gap-4 items-start group">
								<div class="mt-1 w-5 h-5 rounded-full border-2 border-blue-500 cursor-pointer"></div>
								<div class="flex-1">
									<h4 class="font-bold text-gray-900">Strategy call: quarterly review</h4>
									<p class="text-xs text-gray-500 mt-1">Join the team to discuss performance drivers and course correct as needed.</p>
									<div class="text-xs text-gray-400 mt-1">TODAY · 12:30 PM</div>
								</div>
							</div>
						</div>

						<div>
							<div class="text-xs font-bold text-gray-400 mb-2 tracking-wide">NO DUE DATE</div>
							<div class="space-y-3 opacity-60">
								<div class="flex gap-4 items-center">
									<div class="w-5 h-5 rounded-full border-2 border-gray-300"></div>
									<span class="text-sm text-gray-600">Draft Q2 macro notes — 30-min review block</span>
								</div>
								<div class="flex gap-4 items-center">
									<div class="w-5 h-5 rounded-full border-2 border-gray-300"></div>
									<span class="text-sm text-gray-600">Debrief with Davide — strategy feedback session</span>
								</div>
								<div class="flex gap-4 items-center">
									<div class="w-5 h-5 rounded-full border-2 border-gray-300"></div>
									<span class="text-sm text-gray-600">Webinar: market regime shifts</span>
								</div>
							</div>
						</div>
					</div>
				</div>
			</div>

			<div class="flex flex-col md:flex-row gap-8 md:items-start justify-between">
				<div class="flex gap-6 text-sm font-medium text-gray-600">
					<div class="flex items-center gap-2">
						{@html icons.check}
						<span>Investment checklists</span>
					</div>
					<div class="flex items-center gap-2">
						{@html icons.calendar}
						<span>Important reviews</span>
					</div>
					<div class="flex items-center gap-2">
						{@html icons.repeat}
						<span>Recurring tasks</span>
					</div>
				</div>
				<p class="text-xl text-gray-600 max-w-lg leading-relaxed">
					Capture an insight, break down a process, or brainstorm a trade—your agents structure it all into actionable workflows, so you never lose an edge.
				</p>
			</div>
		</section>

		<!-- Who uses it Section -->
<div class="my-12 flex justify-center">
    <img src="/generated/image-a-group-of-diverse-modern-investors-coll-1788861379854-0.webp" alt="Finakets users collaborating" class="rounded-2xl shadow-lg w-full max-w-4xl object-cover" />
</div>
		<section class="max-w-7xl mx-auto px-6 py-20">
			<div class="mb-16">
				<span class="inline-block bg-gray-100 text-gray-700 px-3 py-1 rounded-full text-xs font-semibold uppercase tracking-wide mb-6">
					Use cases
				</span>
				<h2 class="text-4xl md:text-5xl font-bold text-gray-900 mb-6 tracking-tight">
					Who is it for?
				</h2>
				<p class="text-xl text-gray-600 max-w-2xl leading-relaxed">
					Finakets is for ambitious self-directed investors, retail traders, emerging pros, and everyone building their own process.
				</p>
			</div>

			<div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-4">
				<!-- Card 1 -->
				<div class="bg-gray-100 p-6 rounded-xl min-h-[200px] flex flex-col">
					<h3 class="font-bold text-gray-900 mb-2">Journaling decisions</h3>
					<p class="text-xs text-gray-600 mt-auto leading-relaxed">Log every market move, your reasoning, and keep a verifiable track record for lessons learned.</p>
				</div>
				<!-- Card 2 -->
				<div class="bg-gray-100 p-6 rounded-xl min-h-[200px] flex flex-col">
					<h3 class="font-bold text-gray-900 mb-2">Tracking thesis drift</h3>
					<p class="text-xs text-gray-600 mt-auto leading-relaxed">Batch insights, monitor evolving rationales, and spot when conviction needs re-examination.</p>
				</div>
				<!-- Card 3 -->
				<div class="bg-gray-100 p-6 rounded-xl min-h-[200px] flex flex-col">
					<h3 class="font-bold text-gray-900 mb-2">Reviewing performance</h3>
					<p class="text-xs text-gray-600 mt-auto leading-relaxed">Reflect weekly or monthly on process, trade rationale, and identify win/loss patterns.</p>
				</div>
				<!-- Card 4 -->
				<div class="bg-gray-100 p-6 rounded-xl min-h-[200px] flex flex-col">
					<h3 class="font-bold text-gray-900 mb-2">Building systematic strategies</h3>
					<p class="text-xs text-gray-600 mt-auto leading-relaxed">Develop and refine playbooks as living documents, evolving as you learn what works.</p>
				</div>

				<!-- Card 5 -->
				<div class="bg-gray-100 p-6 rounded-xl min-h-[200px] flex flex-col">
					<h3 class="font-bold text-gray-900 mb-2">Progress reviews</h3>
					<p class="text-xs text-gray-600 mt-auto leading-relaxed">Maintain project logs, analyze blockers, and celebrate milestones with traceable context.</p>
				</div>
				<!-- Card 6 -->
				<div class="bg-gray-100 p-6 rounded-xl min-h-[200px] flex flex-col">
					<h3 class="font-bold text-gray-900 mb-2">Defining investing goals</h3>
					<p class="text-xs text-gray-600 mt-auto leading-relaxed">Set process targets for return, risk, or learning, and see progress as it unfolds.</p>
				</div>
				<!-- Card 7 -->
				<div class="bg-gray-100 p-6 rounded-xl min-h-[200px] flex flex-col">
					<h3 class="font-bold text-gray-900 mb-2">Turning analysis into actions</h3>
					<p class="text-xs text-gray-600 mt-auto leading-relaxed">Translate insights into structured, prioritized action steps to execute efficiently.</p>
				</div>
				<!-- Card 8 -->
				<div class="bg-gray-100 p-6 rounded-xl min-h-[200px] flex flex-col">
					<h3 class="font-bold text-gray-900 mb-2">Reviewing/adjusting strategy</h3>
					<p class="text-xs text-gray-600 mt-auto leading-relaxed">Continuously improve—surface new risks, opportunities and adapt approaches with real data.</p>
				</div>

				<!-- Card 9 -->
				<div class="bg-gray-100 p-6 rounded-xl min-h-[200px] flex flex-col">
					<h3 class="font-bold text-gray-900 mb-2">Synthesizing market research</h3>
					<p class="text-xs text-gray-600 mt-auto leading-relaxed">Aggregate scattered research into clear, linked notes for faster analysis.</p>
				</div>
				<!-- Card 10 -->
				<div class="bg-gray-100 p-6 rounded-xl min-h-[200px] flex flex-col">
					<h3 class="font-bold text-gray-900 mb-2">Meeting preparation</h3>
					<p class="text-xs text-gray-600 mt-auto leading-relaxed">Go into portfolio review calls with all the decision context and history surfaced, instantly.</p>
				</div>
				<!-- Card 11 -->
				<div class="bg-gray-100 p-6 rounded-xl min-h-[200px] flex flex-col">
					<h3 class="font-bold text-gray-900 mb-2">Outlining investment memoranda</h3>
					<p class="text-xs text-gray-600 mt-auto leading-relaxed">Shape multi-source insights into drafts for pitches, write-ups, or strategy docs.</p>
				</div>
			</div>
		</section>

		<!-- Footer -->
		<footer class="max-w-7xl mx-auto px-6 py-12 border-t border-gray-100">
			<div class="grid grid-cols-1 md:grid-cols-2 gap-8">
				<div>
					<h4 class="font-bold text-sm text-gray-900 mb-4">Resources</h4>
					<div class="grid grid-cols-2 gap-x-8 gap-y-3 text-xs text-gray-600">
						<a href="#" class="flex items-center gap-2 hover:text-gray-900">
							{@html icons.sparkles} The institutional mindset
						</a>
						<a href="#" class="flex items-center gap-2 hover:text-gray-900">
							{@html icons.plus} Getting started with Finakets
						</a>
						<a href="#" class="flex items-center gap-2 hover:text-gray-900">
							{@html icons.download} Importing old journals
						</a>
						<a href="#" class="flex items-center gap-2 hover:text-gray-900">
							{@html icons.target} Building custom playbooks
						</a>
						<a href="#" class="flex items-center gap-2 hover:text-gray-900">
							{@html icons.reflection} Creating a robust review habit
						</a>
					</div>
				</div>
			</div>

			<div class="flex flex-col md:flex-row justify-between items-center mt-12 pt-8 text-xs text-gray-400">
				<div class="flex items-center gap-2 mb-4 md:mb-0">
					<div class="w-6 h-6 text-gray-300">
						<svg viewBox="0 0 24 24" fill="currentColor" class="w-full h-full">
							<path d="M12 2C13.1 2 14 2.9 14 4C14 5.1 13.1 6 12 6C10.9 6 10 5.1 10 4C10 2.9 10.9 2 12 2ZM12 22C10.9 22 10 21.1 10 20C10 18.9 10.9 18 12 18C13.1 18 14 18.9 14 20C14 21.1 13.1 22 12 22ZM6 12C6 10.9 5.1 10 4 10C2.9 10 2 10.9 2 12C2 13.1 2.9 14 4 14C5.1 14 6 13.1 6 12ZM22 12C22 13.1 21.1 14 20 14C18.9 14 18 13.1 18 12C18 10.9 18.9 10 20 10C21.1 10 22 10.9 22 12ZM17.66 7.34C18.44 6.56 19.7 6.56 20.48 7.34C21.26 8.12 21.26 9.38 20.48 10.16C19.7 10.94 18.44 10.94 17.66 10.16C16.88 9.38 16.88 8.12 17.66 7.34ZM6.34 16.66C5.56 17.44 4.3 17.44 3.52 16.66C2.74 15.88 2.74 14.62 3.52 13.84C4.3 13.06 5.56 13.06 6.34 13.84C7.12 14.62 7.12 15.88 6.34 16.66ZM16.66 17.66C15.88 18.44 15.88 19.7 16.66 20.48C17.44 21.26 18.7 21.26 19.48 20.48C20.26 19.7 20.26 18.44 19.48 17.66C18.7 16.88 18.7 15.62 17.92 14.84L16.66 17.66ZM7.34 6.34C8.12 5.56 8.12 4.3 7.34 3.52C6.56 2.74 5.3 2.74 4.52 3.52C3.74 4.3 3.74 5.56 4.52 6.34C5.3 7.12 6.56 7.12 7.34 6.34Z" />
						</svg>
					</div>
					<div>
						<p>Copyright © 2025 UNMS Technologies Corp.</p>
						<p>All rights reserved. Terms of Service & Privacy Policy.</p>
					</div>
				</div>
				<div class="bg-gray-200 text-gray-600 px-3 py-1 rounded text-xs font-medium">
					Status
				</div>
			</div>
		</footer>

	</main>
</div>

