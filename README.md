[Uploading englishcheck_diagnostic_app.html…]()
# EnglishCheck<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>EnglishCheck - Diagnostic Test Centre</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Google Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&family=Playfair+Display:ital,wght@0,600;0,700;1,600&display=swap" rel="stylesheet">
    <!-- FontAwesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        cream: {
                            50: '#FDFBF7',
                            100: '#FBF9F5',
                            200: '#F4EFE6',
                            300: '#EAE2D3',
                        },
                        brand: {
                            orange: '#E05A36',
                            dark: '#1C1917',
                            muted: '#78716C',
                            accent: '#2563EB'
                        }
                    },
                    fontFamily: {
                        serif: ['Playfair Display', 'Georgia', 'serif'],
                        sans: ['Inter', 'sans-serif']
                    }
                }
            }
        }
    </script>
    <style>
        body {
            background-color: #FBF9F5;
            color: #1C1917;
            background-image: radial-gradient(#EAE2D3 0.75px, transparent 0.75px);
            background-size: 16px 16px;
        }
        .serif-italic {
            font-family: 'Playfair Display', Georgia, serif;
            font-style: italic;
        }
        .drag-over {
            border-style: dashed !important;
            border-color: #E05A36 !important;
            background-color: #FDF4F0 !important;
        }
        .dragging {
            opacity: 0.4;
        }
        ::-webkit-scrollbar {
            width: 6px;
            height: 6px;
        }
        ::-webkit-scrollbar-track {
            background: #F4EFE6;
        }
        ::-webkit-scrollbar-thumb {
            background: #D6CEC0;
            border-radius: 3px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: #A8A090;
        }
    </style>
</head>
<body class="font-sans antialiased min-h-screen flex flex-col justify-between">

    <!-- APP HEADER -->
    <header class="border-b border-stone-200 bg-white/80 backdrop-blur-md sticky top-0 z-50">
        <div class="max-w-6xl mx-auto px-4 sm:px-6 h-16 flex items-center justify-between">
            <div class="flex items-center space-x-3 cursor-pointer" onclick="showView('landing')">
                <span class="text-2xl font-bold font-serif tracking-tight text-stone-900">English<span class="text-brand-orange">Check</span></span>
            </div>
            
            <nav class="flex items-center space-x-6 text-sm font-medium text-stone-600">
                <button onclick="showView('landing')" class="hover:text-stone-900 transition-colors">Diagnostic Hub</button>
                <button onclick="openScoreGuideModal()" class="hover:text-stone-900 transition-colors">Score Guide</button>
                <button onclick="alert('Teacher Portal & Class Analytics connect to LMS backend.')" class="hover:text-stone-900 transition-colors">Teacher Portal</button>
            </nav>
        </div>
    </header>

    <!-- MAIN CONTAINER -->
    <main class="max-w-6xl mx-auto px-4 sm:px-6 py-8 flex-grow w-full">

        <!-- VIEW 1: LANDING HUB -->
        <section id="view-landing" class="block space-y-10">
            <!-- Hero -->
            <div class="max-w-3xl space-y-4 pt-4">
                <p class="text-xs font-semibold tracking-wider text-stone-500 uppercase">DIAGNOSTIC TEST CENTRE</p>
                <h1 class="text-4xl sm:text-5xl md:text-6xl font-serif text-stone-900 font-bold leading-tight">
                    Find out where your English <span class="serif-italic text-brand-orange font-normal">really</span> stands.
                </h1>
                <p class="text-stone-600 text-base sm:text-lg leading-relaxed">
                    Six skill-based diagnostic tests. Each result maps to a CEFR level (A1–C1) and an estimated IELTS band score (3.0–7.0+).
                </p>
            </div>

            <!-- Tests Grid -->
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
                <!-- Grammar (Active) -->
                <div class="bg-white border border-stone-200 rounded-xl p-6 shadow-sm hover:shadow-md transition-all flex flex-col justify-between group">
                    <div>
                        <div class="flex items-center justify-between mb-4">
                            <div class="w-10 h-10 rounded-lg bg-stone-100 flex items-center justify-center text-stone-700">
                                <i class="fa-solid fa-book-open text-lg"></i>
                            </div>
                            <span class="px-2.5 py-1 bg-brand-orange text-white text-xs font-semibold rounded-full">Available</span>
                        </div>
                        <h3 class="text-xl font-serif font-semibold text-stone-900 mb-2">Grammar</h3>
                        <p class="text-xs text-stone-500 mb-4">50 items · 60 minutes · A1–C1 Comprehensive</p>
                        <p class="text-stone-600 text-sm leading-relaxed mb-6">Evaluates structure, syntax, tenses, conditionals, passives, and complex clause patterns.</p>
                    </div>
                    <button onclick="startTest()" class="w-full py-2.5 px-4 bg-stone-900 hover:bg-stone-800 text-white rounded-lg font-medium text-sm flex items-center justify-center space-x-2 transition-colors">
                        <span>Start Test</span>
                        <i class="fa-solid fa-arrow-right text-xs transition-transform group-hover:translate-x-1"></i>
                    </button>
                </div>

                <!-- Vocabulary (Coming Soon) -->
                <div class="bg-white/60 border border-stone-200 rounded-xl p-6 flex flex-col justify-between opacity-80">
                    <div>
                        <div class="flex items-center justify-between mb-4">
                            <div class="w-10 h-10 rounded-lg bg-stone-100 flex items-center justify-center text-stone-500">
                                <i class="fa-solid fa-font text-lg"></i>
                            </div>
                            <span class="px-2.5 py-1 bg-stone-200 text-stone-600 text-xs font-medium rounded-full">Coming soon</span>
                        </div>
                        <h3 class="text-xl font-serif font-semibold text-stone-900 mb-2">Vocabulary</h3>
                        <p class="text-xs text-stone-500 mb-4">Word knowledge & collocations</p>
                        <p class="text-stone-600 text-sm leading-relaxed mb-6">Tests academic lexicon, idiomatic expressions, and collocation accuracy across levels.</p>
                    </div>
                    <button disabled class="w-full py-2.5 px-4 bg-stone-200 text-stone-400 rounded-lg font-medium text-sm cursor-not-allowed">Coming soon</button>
                </div>

                <!-- Reading (Coming Soon) -->
                <div class="bg-white/60 border border-stone-200 rounded-xl p-6 flex flex-col justify-between opacity-80">
                    <div>
                        <div class="flex items-center justify-between mb-4">
                            <div class="w-10 h-10 rounded-lg bg-stone-100 flex items-center justify-center text-stone-500">
                                <i class="fa-solid fa-newspaper text-lg"></i>
                            </div>
                            <span class="px-2.5 py-1 bg-stone-200 text-stone-600 text-xs font-medium rounded-full">Coming soon</span>
                        </div>
                        <h3 class="text-xl font-serif font-semibold text-stone-900 mb-2">Reading</h3>
                        <p class="text-xs text-stone-500 mb-4">Comprehension of diverse texts</p>
                        <p class="text-stone-600 text-sm leading-relaxed mb-6">Measures skimming, scanning, inference, and textual analysis in academic contexts.</p>
                    </div>
                    <button disabled class="w-full py-2.5 px-4 bg-stone-200 text-stone-400 rounded-lg font-medium text-sm cursor-not-allowed">Coming soon</button>
                </div>

                <!-- Listening (Coming Soon) -->
                <div class="bg-white/60 border border-stone-200 rounded-xl p-6 flex flex-col justify-between opacity-80">
                    <div>
                        <div class="flex items-center justify-between mb-4">
                            <div class="w-10 h-10 rounded-lg bg-stone-100 flex items-center justify-center text-stone-500">
                                <i class="fa-solid fa-headphones text-lg"></i>
                            </div>
                            <span class="px-2.5 py-1 bg-stone-200 text-stone-600 text-xs font-medium rounded-full">Coming soon</span>
                        </div>
                        <h3 class="text-xl font-serif font-semibold text-stone-900 mb-2">Listening</h3>
                        <p class="text-xs text-stone-500 mb-4">Audio-based comprehension</p>
                        <p class="text-stone-600 text-sm leading-relaxed mb-6">Evaluates understanding of native accents, lectures, and conversational gist.</p>
                    </div>
                    <button disabled class="w-full py-2.5 px-4 bg-stone-200 text-stone-400 rounded-lg font-medium text-sm cursor-not-allowed">Coming soon</button>
                </div>

                <!-- Speaking (Coming Soon) -->
                <div class="bg-white/60 border border-stone-200 rounded-xl p-6 flex flex-col justify-between opacity-80">
                    <div>
                        <div class="flex items-center justify-between mb-4">
                            <div class="w-10 h-10 rounded-lg bg-stone-100 flex items-center justify-center text-stone-500">
                                <i class="fa-solid fa-microphone text-lg"></i>
                            </div>
                            <span class="px-2.5 py-1 bg-stone-200 text-stone-600 text-xs font-medium rounded-full">Coming soon</span>
                        </div>
                        <h3 class="text-xl font-serif font-semibold text-stone-900 mb-2">Speaking</h3>
                        <p class="text-xs text-stone-500 mb-4">Recorded spoken responses</p>
                        <p class="text-stone-600 text-sm leading-relaxed mb-6">Assesses oral fluency, pronunciation, range, and coherence via speech recognition.</p>
                    </div>
                    <button disabled class="w-full py-2.5 px-4 bg-stone-200 text-stone-400 rounded-lg font-medium text-sm cursor-not-allowed">Coming soon</button>
                </div>

                <!-- Writing (Coming Soon) -->
                <div class="bg-white/60 border border-stone-200 rounded-xl p-6 flex flex-col justify-between opacity-80">
                    <div>
                        <div class="flex items-center justify-between mb-4">
                            <div class="w-10 h-10 rounded-lg bg-stone-100 flex items-center justify-center text-stone-500">
                                <i class="fa-solid fa-pen-nib text-lg"></i>
                            </div>
                            <span class="px-2.5 py-1 bg-stone-200 text-stone-600 text-xs font-medium rounded-full">Coming soon</span>
                        </div>
                        <h3 class="text-xl font-serif font-semibold text-stone-900 mb-2">Writing</h3>
                        <p class="text-xs text-stone-500 mb-4">Short written diagnostic tasks</p>
                        <p class="text-stone-600 text-sm leading-relaxed mb-6">Evaluates essay structure, task achievement, cohesion, and stylistic sophistication.</p>
                    </div>
                    <button disabled class="w-full py-2.5 px-4 bg-stone-200 text-stone-400 rounded-lg font-medium text-sm cursor-not-allowed">Coming soon</button>
                </div>
            </div>
        </section>

        <!-- VIEW 2: TEST INTERFACE -->
        <section id="view-test" class="hidden space-y-6">
            <!-- Header Controls Bar -->
            <div class="bg-white border border-stone-200 rounded-xl p-4 shadow-sm flex flex-wrap items-center justify-between gap-4 sticky top-20 z-40">
                <div>
                    <h2 class="font-serif text-lg font-bold text-stone-900">Grammar Diagnostic Test</h2>
                    <p class="text-xs text-stone-500">50 Items · Max 100 Points</p>
                </div>

                <div class="flex items-center space-x-4">
                    <!-- Timer -->
                    <div class="flex items-center space-x-2 bg-stone-100 px-3 py-1.5 rounded-lg border border-stone-200" id="timer-box">
                        <i class="fa-regular fa-clock text-stone-600"></i>
                        <span id="timer-display" class="font-mono text-sm font-semibold text-stone-800">60:00</span>
                    </div>

                    <!-- Submit Button -->
                    <button onclick="confirmSubmit()" class="px-5 py-2 bg-brand-orange hover:bg-orange-600 text-white rounded-lg text-sm font-semibold shadow-sm transition-colors flex items-center space-x-2">
                        <i class="fa-solid fa-paper-plane text-xs"></i>
                        <span>Submit Test</span>
                    </button>
                </div>
            </div>

            <!-- Main Test Grid -->
            <div class="grid grid-cols-1 lg:grid-cols-4 gap-6">
                <!-- Left Navigator -->
                <div class="lg:col-span-1 space-y-4">
                    <div class="bg-white border border-stone-200 rounded-xl p-4 shadow-sm space-y-3">
                        <div class="flex items-center justify-between">
                            <span class="text-xs font-semibold uppercase text-stone-500 tracking-wider">Progress</span>
                            <span id="progress-text" class="text-xs font-bold text-stone-800">0 / 50</span>
                        </div>
                        <div class="w-full bg-stone-100 h-2 rounded-full overflow-hidden">
                            <div id="progress-bar" class="bg-brand-orange h-full w-0 transition-all duration-300"></div>
                        </div>

                        <div class="pt-2 text-xs font-semibold text-stone-500">Jump to section:</div>
                        <div class="grid grid-cols-5 gap-1 text-center font-mono text-xs">
                            <button onclick="jumpToQuestion(1)" class="py-1 rounded bg-stone-100 hover:bg-stone-200 text-stone-700 font-bold">A1</button>
                            <button onclick="jumpToQuestion(11)" class="py-1 rounded bg-stone-100 hover:bg-stone-200 text-stone-700 font-bold">A2</button>
                            <button onclick="jumpToQuestion(21)" class="py-1 rounded bg-stone-100 hover:bg-stone-200 text-stone-700 font-bold">B1</button>
                            <button onclick="jumpToQuestion(31)" class="py-1 rounded bg-stone-100 hover:bg-stone-200 text-stone-700 font-bold">B2</button>
                            <button onclick="jumpToQuestion(41)" class="py-1 rounded bg-stone-100 hover:bg-stone-200 text-stone-700 font-bold">C1</button>
                        </div>

                        <div class="grid grid-cols-5 gap-1.5 pt-2 max-h-64 lg:max-h-96 overflow-y-auto" id="question-navigator"></div>
                    </div>
                </div>

                <!-- Right Question Active Card -->
                <div class="lg:col-span-3 space-y-6">
                    <div class="bg-white border border-stone-200 rounded-xl p-6 sm:p-8 shadow-sm space-y-6 min-h-[400px]" id="active-question-card"></div>

                    <!-- Prev/Next Navigation -->
                    <div class="flex items-center justify-between pt-2">
                        <button id="btn-prev" onclick="changeQuestion(-1)" class="px-4 py-2 border border-stone-300 bg-white hover:bg-stone-50 rounded-lg text-sm font-medium text-stone-700 flex items-center space-x-2">
                            <i class="fa-solid fa-chevron-left text-xs"></i>
                            <span>Previous</span>
                        </button>
                        <span id="current-item-indicator" class="text-xs font-semibold text-stone-500">Item 1 of 50</span>
                        <button id="btn-next" onclick="changeQuestion(1)" class="px-4 py-2 bg-stone-900 hover:bg-stone-800 text-white rounded-lg text-sm font-medium flex items-center space-x-2">
                            <span>Next</span>
                            <i class="fa-solid fa-chevron-right text-xs"></i>
                        </button>
                    </div>
                </div>
            </div>
        </section>

        <!-- VIEW 3: RESULTS & DIAGNOSTIC DASHBOARD -->
        <section id="view-results" class="hidden space-y-8">
            <div class="bg-white border border-stone-200 rounded-xl p-6 sm:p-8 shadow-sm text-center space-y-4">
                <span class="px-3 py-1 bg-emerald-100 text-emerald-800 text-xs font-semibold rounded-full uppercase tracking-wider">Diagnostic Evaluation Complete</span>
                
                <h2 class="text-3xl sm:text-4xl font-serif font-bold text-stone-900">Your English Proficiency Report</h2>
                
                <div class="grid grid-cols-1 sm:grid-cols-3 gap-4 max-w-2xl mx-auto pt-4">
                    <div class="p-4 bg-stone-50 rounded-xl border border-stone-200">
                        <p class="text-xs font-semibold text-stone-500 uppercase">Total Score</p>
                        <p class="text-3xl font-bold font-serif text-stone-900 mt-1" id="res-score">0 / 100</p>
                        <p class="text-xs text-stone-400 mt-0.5" id="res-raw-items">0 of 50 correct</p>
                    </div>
                    <div class="p-4 bg-stone-50 rounded-xl border border-stone-200">
                        <p class="text-xs font-semibold text-stone-500 uppercase">CEFR Level</p>
                        <p class="text-3xl font-bold font-serif text-brand-orange mt-1" id="res-cefr">--</p>
                        <p class="text-xs text-stone-500 mt-0.5" id="res-cefr-title">Evaluation pending</p>
                    </div>
                    <div class="p-4 bg-stone-50 rounded-xl border border-stone-200">
                        <p class="text-xs font-semibold text-stone-500 uppercase">Est. IELTS Band</p>
                        <p class="text-3xl font-bold font-serif text-blue-600 mt-1" id="res-ielts">--</p>
                        <p class="text-xs text-stone-500 mt-0.5">Overall Grammar Band</p>
                    </div>
                </div>

                <div class="flex flex-wrap items-center justify-center gap-4 pt-4">
                    <button onclick="window.print()" class="px-4 py-2 border border-stone-300 bg-white hover:bg-stone-50 text-stone-700 text-sm font-medium rounded-lg flex items-center space-x-2">
                        <i class="fa-solid fa-print text-xs"></i>
                        <span>Print / Save PDF Report</span>
                    </button>
                    <button onclick="resetAndRestart()" class="px-4 py-2 bg-stone-900 hover:bg-stone-800 text-white text-sm font-medium rounded-lg flex items-center space-x-2">
                        <i class="fa-solid fa-rotate-right text-xs"></i>
                        <span>Retake Diagnostic Test</span>
                    </button>
                </div>
            </div>

            <!-- Skill Breakdown -->
            <div class="bg-white border border-stone-200 rounded-xl p-6 sm:p-8 shadow-sm space-y-4">
                <h3 class="text-xl font-serif font-bold text-stone-900">Grammar Skill Mastery Breakdown</h3>
                <p class="text-xs text-stone-500">Diagnostic performance grouped by core pedagogical categories:</p>
                <div class="grid grid-cols-1 md:grid-cols-2 gap-6 pt-2" id="skill-breakdown-container"></div>
            </div>

            <!-- Item-by-Item Review -->
            <div class="bg-white border border-stone-200 rounded-xl p-6 sm:p-8 shadow-sm space-y-6">
                <div class="flex flex-col sm:flex-row items-start sm:items-center justify-between gap-4">
                    <div>
                        <h3 class="text-xl font-serif font-bold text-stone-900">Item Review & Explanations</h3>
                        <p class="text-xs text-stone-500">Analyze your responses alongside detailed pedagogical explanations.</p>
                    </div>
                    <div class="flex items-center space-x-2 text-xs font-semibold">
                        <button onclick="filterReview('all')" class="px-3 py-1.5 rounded-lg border bg-stone-100 text-stone-800">All (50)</button>
                        <button onclick="filterReview('incorrect')" class="px-3 py-1.5 rounded-lg border bg-white text-rose-600 hover:bg-rose-50">Incorrect</button>
                        <button onclick="filterReview('correct')" class="px-3 py-1.5 rounded-lg border bg-white text-emerald-600 hover:bg-emerald-50">Correct</button>
                    </div>
                </div>

                <div class="space-y-4 divide-y divide-stone-100" id="review-items-list"></div>
            </div>
        </section>

    </main>

    <!-- SCORE GUIDE MODAL -->
    <div id="score-modal" class="fixed inset-0 bg-stone-900/40 backdrop-blur-sm z-50 hidden flex items-center justify-center p-4">
        <div class="bg-white border border-stone-200 rounded-xl max-w-lg w-full p-6 space-y-4 shadow-xl">
            <div class="flex items-center justify-between border-b pb-3 border-stone-100">
                <h3 class="font-serif font-bold text-lg text-stone-900">CEFR & IELTS Band Mapping Scale</h3>
                <button onclick="closeScoreGuideModal()" class="text-stone-400 hover:text-stone-600"><i class="fa-solid fa-xmark text-lg"></i></button>
            </div>
            <div class="space-y-3 text-sm">
                <div class="p-2.5 bg-stone-50 rounded-lg flex items-center justify-between">
                    <div>
                        <span class="font-bold text-stone-900">85 – 100 Points</span>
                        <p class="text-xs text-stone-500">Advanced / Proficient</p>
                    </div>
                    <div class="text-right">
                        <span class="px-2 py-0.5 bg-emerald-100 text-emerald-800 text-xs font-bold rounded">CEFR C1</span>
                        <p class="text-xs text-stone-600 font-semibold mt-0.5">IELTS 7.0 – 8.5+</p>
                    </div>
                </div>
                <div class="p-2.5 bg-stone-50 rounded-lg flex items-center justify-between">
                    <div>
                        <span class="font-bold text-stone-900">65 – 84 Points</span>
                        <p class="text-xs text-stone-500">Upper-Intermediate</p>
                    </div>
                    <div class="text-right">
                        <span class="px-2 py-0.5 bg-blue-100 text-blue-800 text-xs font-bold rounded">CEFR B2</span>
                        <p class="text-xs text-stone-600 font-semibold mt-0.5">IELTS 6.0 – 6.5</p>
                    </div>
                </div>
                <div class="p-2.5 bg-stone-50 rounded-lg flex items-center justify-between">
                    <div>
                        <span class="font-bold text-stone-900">45 – 64 Points</span>
                        <p class="text-xs text-stone-500">Intermediate</p>
                    </div>
                    <div class="text-right">
                        <span class="px-2 py-0.5 bg-amber-100 text-amber-800 text-xs font-bold rounded">CEFR B1</span>
                        <p class="text-xs text-stone-600 font-semibold mt-0.5">IELTS 5.0 – 5.5</p>
                    </div>
                </div>
                <div class="p-2.5 bg-stone-50 rounded-lg flex items-center justify-between">
                    <div>
                        <span class="font-bold text-stone-900">25 – 44 Points</span>
                        <p class="text-xs text-stone-500">Elementary / Pre-Int</p>
                    </div>
                    <div class="text-right">
                        <span class="px-2 py-0.5 bg-orange-100 text-orange-800 text-xs font-bold rounded">CEFR A2</span>
                        <p class="text-xs text-stone-600 font-semibold mt-0.5">IELTS 4.0 – 4.5</p>
                    </div>
                </div>
                <div class="p-2.5 bg-stone-50 rounded-lg flex items-center justify-between">
                    <div>
                        <span class="font-bold text-stone-900">0 – 24 Points</span>
                        <p class="text-xs text-stone-500">Beginner</p>
                    </div>
                    <div class="text-right">
                        <span class="px-2 py-0.5 bg-rose-100 text-rose-800 text-xs font-bold rounded">CEFR A1</span>
                        <p class="text-xs text-stone-600 font-semibold mt-0.5">IELTS 3.0 – 3.5</p>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- FOOTER -->
    <footer class="border-t border-stone-200 bg-white py-6 mt-12">
        <div class="max-w-6xl mx-auto px-4 sm:px-6 flex flex-col sm:flex-row items-center justify-between text-xs text-stone-500 space-y-2 sm:space-y-0">
            <p>© 2026 EnglishCheck EFL Language Assessment Systems. CALL Diagnostic Platform.</p>
            <div class="flex items-center space-x-4">
                <span>50 Items</span>
                <span>•</span>
                <span>A1–C1 Standard</span>
            </div>
        </div>
    </footer>

    <!-- APP SCRIPT & ENGINE -->
    <script>
        const questionsData = [
            // A1 LEVEL (1 to 10)
            {
                id: 1, level: "A1", category: "Tenses & Verb Forms", type: "mcq",
                question: "She _____ to school every morning at 8:00 AM.",
                options: ["walk", "walks", "walking", "is walk"],
                correct: "walks",
                explanation: "Use Present Simple ('walks') for routine daily habits with third-person singular (she)."
            },
            {
                id: 2, level: "A1", category: "Articles & Determiners", type: "mcq",
                question: "Can I have _____ apple from the fruit basket?",
                options: ["a", "an", "the", "some"],
                correct: "an",
                explanation: "Use the indefinite article 'an' before singular countable nouns starting with a vowel sound."
            },
            {
                id: 3, level: "A1", category: "Pronouns & Possessives", type: "mcq",
                question: "This isn't my bag. Is it _____?",
                options: ["you", "your", "yours", "you're"],
                correct: "yours",
                explanation: "'Yours' is a possessive pronoun used standalone without a following noun."
            },
            {
                id: 4, level: "A1", category: "Prepositions", type: "blank",
                question: "My brother was born _____ July 15th.",
                prompt: "preposition",
                correct: "on",
                explanation: "Use the preposition 'on' before specific dates and days of the week."
            },
            {
                id: 5, level: "A1", category: "Tenses & Verb Forms", type: "blank",
                question: "They _____ (be) not at home yesterday evening.",
                prompt: "be / past tense",
                correct: "were",
                explanation: "The past simple of 'to be' for plural subject 'they' is 'were'."
            },
            {
                id: 6, level: "A1", category: "Error Identification", type: "error",
                question: "Click on the underlined segment that contains a grammatical error:",
                sentence: [
                    { label: "A", word: "There" },
                    { label: "B", word: "is" },
                    { label: "C", word: "three books" },
                    { label: "D", word: "on the desk." }
                ],
                correctLabel: "B",
                correct: "are",
                explanation: "Plural noun phrase 'three books' requires plural verb form 'There are' instead of 'There is'."
            },
            {
                id: 7, level: "A1", category: "Plurals & Nouns", type: "mcq",
                question: "How many _____ live in this building?",
                options: ["childs", "children", "child", "childrens"],
                correct: "children",
                explanation: "The irregular plural form of 'child' is 'children'."
            },
            {
                id: 8, level: "A1", category: "Tenses & Verb Forms", type: "blank",
                question: "Look! It _____ (snow) outside right now.",
                prompt: "snow / continuous form",
                correct: "is snowing",
                explanation: "Use Present Continuous ('is snowing') for actions happening at the moment of speaking."
            },
            {
                id: 9, level: "A1", category: "Questions & Negatives", type: "mcq",
                question: "_____ you like tea or coffee?",
                options: ["Does", "Do", "Are", "Have"],
                correct: "Do",
                explanation: "Use auxiliary verb 'Do' for questions in simple present with subject 'you'."
            },
            {
                id: 10, level: "A1", category: "Adjectives & Adverbs", type: "unscramble",
                question: "Drag or reorder the word blocks to form a correct English sentence:",
                words: ["He", "always", "arrives", "early."],
                correctOrder: ["He", "always", "arrives", "early."],
                explanation: "Adverbs of frequency ('always') come before main verbs ('arrives') in basic sentences."
            },

            // A2 LEVEL (11 to 20)
            {
                id: 11, level: "A2", category: "Comparatives & Superlatives", type: "mcq",
                question: "This exam is _____ than the one we took last month.",
                options: ["more difficult", "difficulter", "most difficult", "as difficult"],
                correct: "more difficult",
                explanation: "Long adjectives (like 'difficult') form comparative degrees using 'more + adjective + than'."
            },
            {
                id: 12, level: "A2", category: "Tenses & Verb Forms", type: "blank",
                question: "While I was studying, my sister _____ (cook) dinner.",
                prompt: "cook / continuous past",
                correct: "was cooking",
                explanation: "Use Past Continuous for continuous past actions occurring simultaneously."
            },
            {
                id: 13, level: "A2", category: "Modals & Auxiliaries", type: "mcq",
                question: "You _____ wear a seatbelt when driving; it's the law.",
                options: ["must", "can", "should", "might"],
                correct: "must",
                explanation: "'Must' indicates strong obligation or legal requirement."
            },
            {
                id: 14, level: "A2", category: "Quantifiers & Nouns", type: "mcq",
                question: "How _____ sugar do you take in your coffee?",
                options: ["many", "much", "few", "number of"],
                correct: "much",
                explanation: "Use 'much' with uncountable nouns like 'sugar' in questions."
            },
            {
                id: 15, level: "A2", category: "Future Forms", type: "mcq",
                question: "Look at those dark clouds! It _____ rain.",
                options: ["will", "is going to", "rains", "shall"],
                correct: "is going to",
                explanation: "Use 'be going to' when making predictions based on immediate visual evidence."
            },
            {
                id: 16, level: "A2", category: "Error Identification", type: "error",
                question: "Click on the underlined segment that contains a grammatical error:",
                sentence: [
                    { label: "A", word: "She" },
                    { label: "B", word: "is" },
                    { label: "C", word: "more taller" },
                    { label: "D", word: "than her sister." }
                ],
                correctLabel: "C",
                correct: "taller",
                explanation: "Avoid double comparatives. Short one-syllable adjectives take '-er' ('taller'), not 'more taller'."
            },
            {
                id: 17, level: "A2", category: "Tenses & Verb Forms", type: "blank",
                question: "We have lived in this city _____ five years.",
                prompt: "duration preposition",
                correct: "for",
                explanation: "Use 'for' to denote a duration/period of time ('five years') with present perfect."
            },
            {
                id: 18, level: "A2", category: "Prepositions", type: "mcq",
                question: "He is interested _____ learning foreign languages.",
                options: ["in", "at", "about", "on"],
                correct: "in",
                explanation: "The adjective 'interested' takes the dependent preposition 'in'."
            },
            {
                id: 19, level: "A2", category: "Questions & Auxiliary", type: "mcq",
                question: "She likes ice cream, _____ she?",
                options: ["isn't", "doesn't", "don't", "hasn't"],
                correct: "doesn't",
                explanation: "Present simple positive statement requires negative question tag ('doesn't she?')."
            },
            {
                id: 20, level: "A2", category: "Unscramble Syntax", type: "unscramble",
                question: "Drag or reorder the blocks to build a correct question:",
                words: ["Have", "you", "ever", "been", "to", "Japan?"],
                correctOrder: ["Have", "you", "ever", "been", "to", "Japan?"],
                explanation: "Present Perfect question order: Auxiliary Have + subject + ever + past participle."
            },

            // B1 LEVEL (21 to 30)
            {
                id: 21, level: "B1", category: "Tenses & Verb Forms", type: "mcq",
                question: "I _____ my key! Now I cannot open the front door.",
                options: ["lost", "have lost", "was losing", "had lost"],
                correct: "have lost",
                explanation: "Present Perfect ('have lost') connects a past action to a present result."
            },
            {
                id: 22, level: "B1", category: "Conditionals", type: "blank",
                question: "If it rains tomorrow, we _____ (cancel) the outdoor picnic.",
                prompt: "cancel / future conditional",
                correct: "will cancel",
                explanation: "First Conditional: If + Present Simple, ... Future Simple ('will cancel')."
            },
            {
                id: 23, level: "B1", category: "Relative Clauses", type: "mcq",
                question: "The woman _____ spoke to you yesterday is my English professor.",
                options: ["which", "who", "whose", "whom"],
                correct: "who",
                explanation: "Use relative pronoun 'who' to refer to human subjects."
            },
            {
                id: 24, level: "B1", category: "Passive Voice", type: "mcq",
                question: "The new bridge _____ by the engineering company last year.",
                options: ["built", "was built", "is built", "has been built"],
                correct: "was built",
                explanation: "Past Simple Passive: Subject + was/were + past participle ('was built')."
            },
            {
                id: 25, level: "B1", category: "Conditionals", type: "mcq",
                question: "If I had more free time, I _____ learn to play the violin.",
                options: ["will", "would", "can", "shall"],
                correct: "would",
                explanation: "Second Conditional: If + Past Simple, ... would + bare infinitive."
            },
            {
                id: 26, level: "B1", category: "Gerunds & Infinitives", type: "blank",
                question: "I am really looking forward to _____ (see) you next week.",
                prompt: "see / gerund form",
                correct: "seeing",
                explanation: "'Look forward to' requires a gerund (-ing form)."
            },
            {
                id: 27, level: "B1", category: "Error Identification", type: "error",
                question: "Click on the underlined segment that contains a grammatical error:",
                sentence: [
                    { label: "A", word: "He" },
                    { label: "B", word: "suggested" },
                    { label: "C", word: "to go" },
                    { label: "D", word: "to the cinema tonight." }
                ],
                correctLabel: "C",
                correct: "going",
                explanation: "'Suggest' is followed by a gerund ('suggested going'), NOT a to-infinitive."
            },
            {
                id: 28, level: "B1", category: "Modals & Auxiliaries", type: "mcq",
                question: "You _____ bring an umbrella; it isn't going to rain.",
                options: ["must not", "don't have to", "could not", "should not"],
                correct: "don't have to",
                explanation: "'Don't have to' expresses lack of necessity/obligation."
            },
            {
                id: 29, level: "B1", category: "Reported Speech", type: "blank",
                question: "She told me that she _____ (finish) her homework earlier.",
                prompt: "finish / past perfect",
                correct: "had finished",
                explanation: "Reported speech backshifts past simple to Past Perfect ('had finished')."
            },
            {
                id: 30, level: "B1", category: "Unscramble Syntax", type: "unscramble",
                question: "Drag or reorder the blocks to form a relative clause sentence:",
                words: ["Rome", "is the city", "where", "my father", "was born."],
                correctOrder: ["Rome", "is the city", "where", "my father", "was born."],
                explanation: "Main clause 'Rome is the city' linked by relative adverb 'where'."
            },

            // B2 LEVEL (31 to 40)
            {
                id: 31, level: "B2", category: "Conditionals", type: "mcq",
                question: "If we _____ earlier, we wouldn't have missed the flight.",
                options: ["left", "had left", "have left", "would leave"],
                correct: "had left",
                explanation: "Third Conditional: If + Past Perfect ('had left'), ... would have + past participle."
            },
            {
                id: 32, level: "B2", category: "Modals of Deduction", type: "blank",
                question: "The lights are off and her car isn't here. She _____ (must / leave) already.",
                prompt: "modals of past deduction",
                correct: "must have left",
                explanation: "'Must have + past participle' expresses logical deduction about past events."
            },
            {
                id: 33, level: "B2", category: "Wish & Hypotheticals", type: "mcq",
                question: "I wish I _____ so much money on that expensive coat yesterday.",
                options: ["didn't spend", "hadn't spent", "wouldn't spend", "don't spend"],
                correct: "hadn't spent",
                explanation: "Use 'wish + Past Perfect' to express regret about past actions."
            },
            {
                id: 34, level: "B2", category: "Indirect Questions", type: "mcq",
                question: "Could you tell me where _____?",
                options: ["the train station is", "is the train station", "the train station was", "does the train station lie"],
                correct: "the train station is",
                explanation: "Indirect questions adopt statement word order (Subject + Verb)."
            },
            {
                id: 35, level: "B2", category: "Advanced Passives", type: "mcq",
                question: "The CEO is believed _____ the country early yesterday morning.",
                options: ["to leave", "to have left", "leaving", "that he left"],
                correct: "to have left",
                explanation: "Personal passive with prior time reference: Subject + passive verb + perfect infinitive."
            },
            {
                id: 36, level: "B2", category: "Error Identification", type: "error",
                question: "Click on the underlined segment that contains a grammatical error:",
                sentence: [
                    { label: "A", word: "Despite" },
                    { label: "B", word: "he was tired," },
                    { label: "C", word: "he finished" },
                    { label: "D", word: "the report on time." }
                ],
                correctLabel: "A",
                correct: "Although",
                explanation: "'Despite' must be followed by a noun phrase/gerund. A full clause requires 'Although'."
            },
            {
                id: 37, level: "B2", category: "Causative Verbs", type: "blank",
                question: "We need to get our roof _____ (repair) before winter.",
                prompt: "repair / causative past participle",
                correct: "repaired",
                explanation: "Passive causative structure: 'get + object + past participle'."
            },
            {
                id: 38, level: "B2", category: "Mixed Conditionals", type: "mcq",
                question: "If I had taken your advice back then, I _____ in trouble now.",
                options: ["won't be", "wouldn't be", "hadn't been", "am not"],
                correct: "wouldn't be",
                explanation: "Mixed Conditional: Past condition ('had taken') with present result ('wouldn't be')."
            },
            {
                id: 39, level: "B2", category: "Articles & Determiners", type: "mcq",
                question: "_____ doctor I talked to recommended taking a few days of rest.",
                options: ["A", "The", "An", "Zero article"],
                correct: "The",
                explanation: "Use 'The' because the noun is specified by the relative clause."
            },
            {
                id: 40, level: "B2", category: "Unscramble Syntax", type: "unscramble",
                question: "Drag or reorder the blocks to build a reported speech sentence:",
                words: ["The guard", "strictly", "warned us", "not to enter", "the restricted area."],
                correctOrder: ["The guard", "strictly", "warned us", "not to enter", "the restricted area."],
                explanation: "Reporting order: Subject + adverb + verb + object + negative infinitive."
            },

            // C1 LEVEL (41 to 50)
            {
                id: 41, level: "C1", category: "Inversion Syntax", type: "mcq",
                question: "Rarely _____ such a captivating theatrical performance.",
                options: ["I have seen", "have I seen", "did I saw", "I saw"],
                correct: "have I seen",
                explanation: "Negative adverbials ('Rarely') at the start trigger subject-auxiliary inversion."
            },
            {
                id: 42, level: "C1", category: "Subjunctive Mood", type: "blank",
                question: "The board of directors insisted that the project _____ (halt) immediately.",
                prompt: "halt / base subjunctive form",
                correct: "be halted",
                explanation: "Mandative subjunctive mood uses base form ('be halted') in that-clauses after insistence."
            },
            {
                id: 43, level: "C1", category: "Participle Clauses", type: "mcq",
                question: "_____ all the financial reports, the auditor identified several discrepancies.",
                options: ["Having examined", "Examined", "On examining", "To examine"],
                correct: "Having examined",
                explanation: "Perfect participle clause ('Having examined') indicates prior completion."
            },
            {
                id: 44, level: "C1", category: "Advanced Inversion", type: "mcq",
                question: "Had I known about the changes earlier, I _____ my flight schedule.",
                options: ["would adjust", "would have adjusted", "had adjusted", "adjusted"],
                correct: "would have adjusted",
                explanation: "Inverted 3rd Conditional: 'Had I known' paired with 'would have + past participle'."
            },
            {
                id: 45, level: "C1", category: "Error Identification", type: "error",
                question: "Click on the underlined segment that contains a grammatical error:",
                sentence: [
                    { label: "A", word: "No sooner" },
                    { label: "B", word: "had he arrived" },
                    { label: "C", word: "when" },
                    { label: "D", word: "the meeting started." }
                ],
                correctLabel: "C",
                correct: "than",
                explanation: "'No sooner...' must be paired with 'than', NOT 'when'."
            },
            {
                id: 46, level: "C1", category: "Cleft Sentences", type: "blank",
                question: "It was only when the rain stopped _____ we ventured outside.",
                prompt: "cleft connector",
                correct: "that",
                explanation: "It-cleft structure: 'It + be + focus phrase + THAT + main clause'."
            },
            {
                id: 47, level: "C1", category: "Advanced Prepositions", type: "mcq",
                question: "The new regulations were implemented _____ compliance with European law.",
                options: ["in view of", "in accordance with", "with regard to", "on behalf of"],
                correct: "in accordance with",
                explanation: "'In accordance with' means conforming to or following a rule or law."
            },
            {
                id: 48, level: "C1", category: "Subjunctive & Wish", type: "mcq",
                question: "It is high time the committee _____ a final decision on this matter.",
                options: ["reach", "reached", "has reached", "should reach"],
                correct: "reached",
                explanation: "'It is high time + subject' requires Past Simple (unreal past)."
            },
            {
                id: 49, level: "C1", category: "Advanced Syntax", type: "blank",
                question: "Try _____ he might, he could not crack the complex cryptographic code.",
                prompt: "concessive connector",
                correct: "as",
                explanation: "Concessive structure: 'Verb + as + subject + might' ('Try as he might')."
            },
            {
                id: 50, level: "C1", category: "Unscramble Advanced Clause", type: "unscramble",
                question: "Drag or reorder the blocks to form an advanced C1 cleft sentence:",
                words: ["What impressed us", "most", "during the interview", "was her exceptional", "problem-solving ability."],
                correctOrder: ["What impressed us", "most", "during the interview", "was her exceptional", "problem-solving ability."],
                explanation: "Wh-cleft sentence placing focal emphasis on the noun phrase at the predicate position."
            }
        ];

        // --- STATE ENGINE ---
        let currentQuestionIdx = 0;
        let userAnswers = {}; // { questionId: value }
        let timerSeconds = 3600;
        let timerInterval = null;

        function showView(viewId) {
            document.getElementById('view-landing').classList.add('hidden');
            document.getElementById('view-test').classList.add('hidden');
            document.getElementById('view-results').classList.add('hidden');
            document.getElementById('view-' + viewId).classList.remove('hidden');
            window.scrollTo({ top: 0, behavior: 'smooth' });
        }

        function openScoreGuideModal() { document.getElementById('score-modal').classList.remove('hidden'); }
        function closeScoreGuideModal() { document.getElementById('score-modal').classList.add('hidden'); }

        function startTest() {
            userAnswers = {};
            currentQuestionIdx = 0;
            timerSeconds = 3600;
            showView('test');
            renderQuestionNavigator();
            renderQuestion(currentQuestionIdx);
            startTimer();
        }

        function startTimer() {
            if (timerInterval) clearInterval(timerInterval);
            updateTimerDisplay();
            timerInterval = setInterval(() => {
                timerSeconds--;
                updateTimerDisplay();
                if (timerSeconds <= 0) {
                    clearInterval(timerInterval);
                    alert("Time is up! Submitting test.");
                    submitTest();
                }
            }, 1000);
        }

        function updateTimerDisplay() {
            const mins = Math.floor(timerSeconds / 60);
            const secs = timerSeconds % 60;
            const displayStr = `${mins.toString().padStart(2, '0')}:${secs.toString().padStart(2, '0')}`;
            const box = document.getElementById('timer-box');
            const display = document.getElementById('timer-display');
            display.textContent = displayStr;
            if (timerSeconds < 300) {
                box.classList.add('bg-rose-100', 'border-rose-300');
                display.classList.add('text-rose-700');
            } else {
                box.classList.remove('bg-rose-100', 'border-rose-300');
                display.classList.remove('text-rose-700');
            }
        }

        function renderQuestionNavigator() {
            const nav = document.getElementById('question-navigator');
            nav.innerHTML = '';
            questionsData.forEach((q, idx) => {
                const btn = document.createElement('button');
                btn.id = `nav-btn-${idx}`;
                btn.className = `w-full h-8 text-xs font-medium rounded transition-all flex items-center justify-center border `;
                
                const hasAnswer = userAnswers[q.id] !== undefined && userAnswers[q.id] !== null && String(userAnswers[q.id]).trim() !== '';

                if (idx === currentQuestionIdx) {
                    btn.className += 'border-stone-900 bg-stone-900 text-white font-bold ring-2 ring-stone-400/50';
                } else if (hasAnswer) {
                    btn.className += 'border-emerald-500 bg-emerald-50 text-emerald-800 font-semibold';
                } else {
                    btn.className += 'border-stone-200 bg-white hover:bg-stone-50 text-stone-700';
                }
                btn.textContent = q.id;
                btn.onclick = () => jumpToQuestion(idx + 1);
                nav.appendChild(btn);
            });

            const answeredCount = Object.keys(userAnswers).filter(k => userAnswers[k] !== undefined && String(userAnswers[k]).trim() !== '').length;
            document.getElementById('progress-text').textContent = `${answeredCount} / 50`;
            document.getElementById('progress-bar').style.width = `${(answeredCount / 50) * 100}%`;
        }

        function jumpToQuestion(num1Based) {
            currentQuestionIdx = num1Based - 1;
            renderQuestion(currentQuestionIdx);
            renderQuestionNavigator();
        }

        function changeQuestion(delta) {
            const nextIdx = currentQuestionIdx + delta;
            if (nextIdx >= 0 && nextIdx < questionsData.length) {
                currentQuestionIdx = nextIdx;
                renderQuestion(currentQuestionIdx);
                renderQuestionNavigator();
            }
        }

        function renderQuestion(idx) {
            const q = questionsData[idx];
            const card = document.getElementById('active-question-card');
            
            let html = `
                <div class="flex items-center justify-between border-b border-stone-100 pb-4">
                    <div class="flex items-center space-x-3">
                        <span class="w-8 h-8 rounded-full bg-stone-900 text-white font-bold text-xs flex items-center justify-center">${q.id}</span>
                        <div>
                            <span class="text-xs font-semibold px-2 py-0.5 rounded bg-stone-100 text-stone-700 uppercase tracking-wider">${q.level} Level</span>
                            <span class="text-xs text-stone-400 ml-2">${q.category}</span>
                        </div>
                    </div>
                    <span class="text-xs text-stone-400 font-medium">Value: 2.0 Pts</span>
                </div>
                <h3 class="text-lg font-semibold text-stone-900 leading-snug">${q.question}</h3>
            `;

            // TYPE 1: MCQ
            if (q.type === 'mcq') {
                html += `<div class="space-y-3 pt-2">`;
                q.options.forEach(opt => {
                    const isChecked = userAnswers[q.id] === opt;
                    html += `
                        <label class="flex items-center p-3.5 rounded-xl border ${isChecked ? 'border-brand-orange bg-orange-50/50 ring-2 ring-brand-orange' : 'border-stone-200 hover:border-stone-300 bg-white'} cursor-pointer transition-all">
                            <input type="radio" name="q_${q.id}" value="${escapeQuote(opt)}" ${isChecked ? 'checked' : ''} onchange="saveAnswer(${q.id}, '${escapeQuote(opt)}')" class="w-4 h-4 text-brand-orange focus:ring-brand-orange">
                            <span class="ml-3 text-sm font-medium text-stone-800">${escapeHtml(opt)}</span>
                        </label>
                    `;
                });
                html += `</div>`;
            } 

            // TYPE 2: FILL-IN-THE-BLANK (DIRECT TYPING)
            else if (q.type === 'blank') {
                const currentVal = userAnswers[q.id] || '';
                html += `
                    <div class="pt-2 space-y-3">
                        <label class="block text-xs font-semibold text-stone-500 uppercase tracking-wider">Type your answer in the box below (${q.prompt}):</label>
                        <div class="flex items-center space-x-3">
                            <input type="text" id="blank_input_${q.id}" value="${escapeHtml(currentVal)}" oninput="saveAnswer(${q.id}, this.value)" placeholder="Type answer here..." class="w-full sm:w-80 p-3 rounded-lg border border-stone-300 bg-white text-stone-900 font-medium text-base focus:ring-2 focus:ring-brand-orange focus:border-brand-orange focus:outline-none shadow-sm">
                        </div>
                    </div>
                `;
            }

            // TYPE 3: ERROR IDENTIFICATION WITH ILLUMINATED SELECTION
            else if (q.type === 'error') {
                const currentVal = userAnswers[q.id]; // Stores chosen segment label (e.g. 'B')
                html += `
                    <div class="space-y-4 pt-2">
                        <p class="text-xs text-stone-500">Select the option corresponding to the incorrect segment:</p>
                        <div class="p-4 sm:p-6 bg-stone-50 rounded-xl border border-stone-200 flex flex-wrap gap-3 items-center text-base leading-relaxed">
                            ${q.sentence.map(seg => {
                                const isSelected = currentVal === seg.label;
                                return `
                                    <button onclick="saveAnswer(${q.id}, '${seg.label}')" class="px-3.5 py-2 rounded-lg font-medium transition-all flex items-center space-x-2 border ${isSelected ? 'bg-brand-orange text-white border-brand-orange shadow-md scale-105 font-bold ring-2 ring-orange-300' : 'bg-white text-stone-800 border-stone-300 hover:bg-stone-100 hover:border-stone-400'}">
                                        <span class="text-xs px-1.5 py-0.5 rounded ${isSelected ? 'bg-white/30 text-white font-bold' : 'bg-stone-200 text-stone-700'}">[${seg.label}]</span>
                                        <span>${escapeHtml(seg.word)}</span>
                                    </button>
                                `;
                            }).join('')}
                        </div>
                    </div>
                `;
            }

            // TYPE 4: DRAG AND DROP / REORDER SENTENCE
            else if (q.type === 'unscramble') {
                let currentArray = userAnswers[q.id] ? userAnswers[q.id].split(' || ') : [...q.words];
                
                html += `
                    <div class="space-y-4 pt-2">
                        <p class="text-xs text-stone-500">Drag items to rearrange them into correct order (or use the arrow buttons):</p>
                        <div id="drag-container-${q.id}" class="flex flex-wrap gap-2 p-4 bg-stone-50 rounded-xl border border-stone-200 min-h-[70px]">
                            ${currentArray.map((w, wIdx) => `
                                <div draggable="true" ondragstart="onDragStart(event, ${wIdx})" ondragover="onDragOver(event)" ondrop="onDrop(event, ${wIdx}, ${q.id})" class="cursor-grab active:cursor-grabbing px-3.5 py-2 bg-white border border-stone-300 rounded-lg text-sm font-semibold text-stone-800 shadow-sm flex items-center space-x-2 hover:border-brand-orange transition-all">
                                    <i class="fa-solid fa-grip-vertical text-stone-400 text-xs"></i>
                                    <span>${escapeHtml(w)}</span>
                                    <span class="text-stone-300">|</span>
                                    <button onclick="shiftWord(${q.id}, ${wIdx}, -1)" class="text-stone-400 hover:text-stone-700 text-xs px-1">←</button>
                                    <button onclick="shiftWord(${q.id}, ${wIdx}, 1)" class="text-stone-400 hover:text-stone-700 text-xs px-1">→</button>
                                </div>
                            `).join('')}
                        </div>
                    </div>
                `;
            }

            card.innerHTML = html;
            document.getElementById('current-item-indicator').textContent = `Item ${idx + 1} of 50`;
            document.getElementById('btn-prev').disabled = idx === 0;
            document.getElementById('btn-next').disabled = idx === questionsData.length - 1;
        }

        // --- DRAG AND DROP HANDLERS ---
        let draggedIndex = null;
        function onDragStart(e, idx) {
            draggedIndex = idx;
            e.dataTransfer.effectAllowed = 'move';
        }

        function onDragOver(e) {
            e.preventDefault();
            e.dataTransfer.dropEffect = 'move';
        }

        function onDrop(e, targetIdx, qId) {
            e.preventDefault();
            if (draggedIndex === null || draggedIndex === targetIdx) return;
            
            const q = questionsData.find(item => item.id === qId);
            let currentArray = userAnswers[qId] ? userAnswers[qId].split(' || ') : [...q.words];
            
            const movedItem = currentArray.splice(draggedIndex, 1)[0];
            currentArray.splice(targetIdx, 0, movedItem);
            
            saveAnswer(qId, currentArray.join(' || '));
            renderQuestion(currentQuestionIdx);
        }

        function shiftWord(qId, index, direction) {
            const q = questionsData.find(item => item.id === qId);
            let currentArray = userAnswers[qId] ? userAnswers[qId].split(' || ') : [...q.words];
            const targetIdx = index + direction;
            if (targetIdx < 0 || targetIdx >= currentArray.length) return;
            
            const temp = currentArray[index];
            currentArray[index] = currentArray[targetIdx];
            currentArray[targetIdx] = temp;
            
            saveAnswer(qId, currentArray.join(' || '));
            renderQuestion(currentQuestionIdx);
        }

        function saveAnswer(questionId, val) {
            userAnswers[questionId] = val;
            renderQuestionNavigator();
            if (questionsData[currentQuestionIdx].type === 'error') {
                renderQuestion(currentQuestionIdx);
            }
        }

        function confirmSubmit() {
            const answeredCount = Object.keys(userAnswers).filter(k => userAnswers[k] !== undefined && String(userAnswers[k]).trim() !== '').length;
            const remaining = 50 - answeredCount;
            let msg = "Are you sure you want to submit your test?";
            if (remaining > 0) {
                msg = `You have ${remaining} unanswered item(s). Are you sure you wish to submit early?`;
            }
            if (confirm(msg)) {
                submitTest();
            }
        }

        function forceSubmitTest() {
            if (timerInterval) clearInterval(timerInterval);
            submitTest();
        }

        function submitTest() {
            if (timerInterval) clearInterval(timerInterval);

            let totalScore = 0;
            let rawCorrect = 0;
            const skillStats = {};

            questionsData.forEach(q => {
                if (!skillStats[q.category]) {
                    skillStats[q.category] = { total: 0, correct: 0 };
                }
                skillStats[q.category].total += 2;

                const userVal = userAnswers[q.id];
                let isCorrect = false;

                if (q.type === 'mcq') {
                    if (userVal === q.correct) isCorrect = true;
                } else if (q.type === 'blank') {
                    if (userVal && userVal.trim().toLowerCase() === q.correct.trim().toLowerCase()) {
                        isCorrect = true;
                    }
                } else if (q.type === 'error') {
                    if (userVal === q.correctLabel) isCorrect = true;
                } else if (q.type === 'unscramble') {
                    if (userVal === q.correctOrder.join(' || ')) isCorrect = true;
                }

                if (isCorrect) {
                    totalScore += 2;
                    rawCorrect++;
                    skillStats[q.category].correct += 2;
                }
            });

            // Mapping CEFR & IELTS
            let cefr = "A1";
            let cefrTitle = "Beginner";
            let ielts = "3.0 – 3.5";

            if (totalScore >= 85) { cefr = "C1"; cefrTitle = "Advanced / Proficient"; ielts = "7.0 – 8.5+"; }
            else if (totalScore >= 65) { cefr = "B2"; cefrTitle = "Upper-Intermediate"; ielts = "6.0 – 6.5"; }
            else if (totalScore >= 45) { cefr = "B1"; cefrTitle = "Intermediate"; ielts = "5.0 – 5.5"; }
            else if (totalScore >= 25) { cefr = "A2"; cefrTitle = "Elementary / Pre-Int"; ielts = "4.0 – 4.5"; }

            document.getElementById('res-score').textContent = `${totalScore} / 100`;
            document.getElementById('res-raw-items').textContent = `${rawCorrect} of 50 items correct`;
            document.getElementById('res-cefr').textContent = cefr;
            document.getElementById('res-cefr-title').textContent = cefrTitle;
            document.getElementById('res-ielts').textContent = ielts;

            // Skill Breakdown UI
            const breakdownContainer = document.getElementById('skill-breakdown-container');
            breakdownContainer.innerHTML = '';
            for (const [cat, data] of Object.entries(skillStats)) {
                const pct = Math.round((data.correct / data.total) * 100);
                breakdownContainer.innerHTML += `
                    <div class="space-y-1.5 p-3.5 bg-stone-50 rounded-lg border border-stone-200">
                        <div class="flex items-center justify-between text-xs font-semibold">
                            <span class="text-stone-800">${cat}</span>
                            <span class="text-stone-600">${data.correct}/${data.total} pts (${pct}%)</span>
                        </div>
                        <div class="w-full bg-stone-200 h-2 rounded-full overflow-hidden">
                            <div class="bg-brand-orange h-full" style="width: ${pct}%"></div>
                        </div>
                    </div>
                `;
            }

            renderReviewList('all');
            showView('results');
        }

        function filterReview(filter) { renderReviewList(filter); }

        function renderReviewList(filter) {
            const reviewContainer = document.getElementById('review-items-list');
            reviewContainer.innerHTML = '';

            questionsData.forEach(q => {
                const userVal = userAnswers[q.id];
                let isCorrect = false;

                let formattedUserAns = userVal;
                let formattedCorrectAns = q.correct;

                if (q.type === 'unscramble') {
                    formattedUserAns = userVal ? userVal.split(' || ').join(' ') : 'Unanswered';
                    formattedCorrectAns = q.correctOrder.join(' ');
                    if (userVal === q.correctOrder.join(' || ')) isCorrect = true;
                } else if (q.type === 'error') {
                    const foundSeg = q.sentence.find(s => s.label === userVal);
                    formattedUserAns = userVal ? `[${userVal}] ${foundSeg ? foundSeg.word : ''}` : 'Unanswered';
                    formattedCorrectAns = `[${q.correctLabel}] Correction: "${q.correct}"`;
                    if (userVal === q.correctLabel) isCorrect = true;
                } else if (q.type === 'blank') {
                    formattedUserAns = userVal ? userVal.trim() : 'Unanswered';
                    if (userVal && userVal.trim().toLowerCase() === q.correct.trim().toLowerCase()) isCorrect = true;
                } else {
                    if (!formattedUserAns) formattedUserAns = 'Unanswered';
                    if (userVal === q.correct) isCorrect = true;
                }

                if (filter === 'correct' && !isCorrect) return;
                if (filter === 'incorrect' && isCorrect) return;

                reviewContainer.innerHTML += `
                    <div class="pt-4 space-y-2">
                        <div class="flex items-start justify-between gap-2">
                            <div class="space-y-1">
                                <div class="flex items-center space-x-2">
                                    <span class="px-2 py-0.5 rounded text-xs font-bold ${isCorrect ? 'bg-emerald-100 text-emerald-800' : 'bg-rose-100 text-rose-800'}">
                                        Item ${q.id} ${isCorrect ? '✓ Correct' : '✗ Incorrect'}
                                    </span>
                                    <span class="text-xs font-semibold px-2 py-0.5 rounded bg-stone-100 text-stone-600">${q.level}</span>
                                    <span class="text-xs text-stone-400">${q.category}</span>
                                </div>
                                <h4 class="text-sm font-semibold text-stone-900 pt-1">${q.question}</h4>
                            </div>
                            <span class="text-xs font-mono font-bold text-stone-500">${isCorrect ? '+2 pts' : '0 pts'}</span>
                        </div>

                        <div class="grid grid-cols-1 sm:grid-cols-2 gap-2 text-xs pt-1">
                            <div class="p-2.5 rounded-lg ${isCorrect ? 'bg-emerald-50 border border-emerald-200 text-emerald-900' : 'bg-rose-50 border border-rose-200 text-rose-900'}">
                                <span class="font-bold">Your Answer:</span> ${escapeHtml(formattedUserAns)}
                            </div>
                            <div class="p-2.5 rounded-lg bg-stone-50 border border-stone-200 text-stone-900">
                                <span class="font-bold">Correct Key:</span> ${escapeHtml(formattedCorrectAns)}
                            </div>
                        </div>

                        <div class="p-3 bg-amber-50/70 border border-amber-200 rounded-lg text-xs text-amber-900 space-y-1">
                            <span class="font-bold block text-amber-950">Grammar Explanation:</span>
                            <p class="leading-relaxed">${q.explanation}</p>
                        </div>
                    </div>
                `;
            });
        }

        function resetAndRestart() {
            if (confirm("Restart test? All current answers will be cleared.")) {
                startTest();
            }
        }

        function escapeHtml(str) {
            if (!str) return '';
            return String(str).replace(/&/g, "&amp;").replace(/</g, "&lt;").replace(/>/g, "&gt;").replace(/"/g, "&quot;");
        }
        function escapeQuote(str) {
            if (!str) return '';
            return String(str).replace(/'/g, "\\'");
        }
    </script>
</body>
</html>
