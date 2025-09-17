# Team Retrospective Icebreaker Application

A modern, interactive web application designed to help teams break the ice before retrospective meetings. This application provides various engaging activities to get team members talking and connecting.

## Features

### 🎯 Six Different Icebreaker Activities

1. **Random Questions** - Thought-provoking questions to spark meaningful conversation
2. **Would You Rather** - Fun dilemmas that get everyone thinking and sharing
3. **Mood Check-in** - Interactive mood selection to help team members share how they're feeling
4. **Two Truths & a Lie** - Classic game to help teammates learn about each other
5. **Word Association** - Quick energizing games to get creative juices flowing
6. **Gratitude Circle** - Positive sharing activities to build team appreciation

### ✨ Key Features

- **Beautiful Modern UI** - Clean, professional design with smooth animations
- **Mobile Responsive** - Works perfectly on all devices
- **Interactive Elements** - Hover effects, click animations, and engaging interactions
- **Randomized Content** - Shuffle feature ensures fresh content every time
- **Easy Navigation** - Simple back and forth navigation between activities
- **No Dependencies** - Pure HTML, CSS, and JavaScript - no frameworks required

## How to Use

1. Save the code below as `index.html`
2. Open the file in any modern web browser
3. Choose an icebreaker activity from the main menu
4. Use the "Next" button to cycle through different prompts
5. Use the "Shuffle" button to randomize the order
6. Click "Back to Activities" to try a different icebreaker

## Perfect For

- **Team Retrospectives** - Warm up the team before diving into sprint reviews
- **Stand-up Meetings** - Add some fun to daily standups
- **Team Building Sessions** - Break down barriers and build connections
- **Remote Teams** - Especially valuable for distributed teams
- **New Team Members** - Help integrate new people into the team
- **Meeting Energizers** - Re-energize long meetings

## Complete Application Code

Create a file called `index.html` and paste the following code:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Team Retrospective Icebreakers</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            color: #333;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }

        header {
            text-align: center;
            margin-bottom: 40px;
            color: white;
        }

        header h1 {
            font-size: 3rem;
            margin-bottom: 10px;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
        }

        header p {
            font-size: 1.2rem;
            opacity: 0.9;
        }

        .activity-selector h2 {
            text-align: center;
            margin-bottom: 30px;
            color: white;
            font-size: 2rem;
        }

        .activity-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
            margin-bottom: 40px;
        }

        .activity-card {
            background: white;
            border-radius: 15px;
            padding: 30px;
            text-align: center;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
        }

        .activity-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(0,0,0,0.2);
        }

        .activity-icon {
            font-size: 3rem;
            margin-bottom: 15px;
        }

        .activity-card h3 {
            font-size: 1.5rem;
            margin-bottom: 10px;
            color: #333;
        }

        .activity-card p {
            color: #666;
            font-size: 1rem;
        }

        .activity-content {
            background: white;
            border-radius: 15px;
            padding: 30px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
        }

        .activity-header {
            display: flex;
            align-items: center;
            margin-bottom: 30px;
        }

        .back-btn {
            background: #f0f0f0;
            border: none;
            padding: 10px 20px;
            border-radius: 8px;
            cursor: pointer;
            margin-right: 20px;
            font-size: 1rem;
            transition: background 0.3s ease;
        }

        .back-btn:hover {
            background: #e0e0e0;
        }

        .card {
            background: #f8f9fa;
            border-radius: 12px;
            padding: 40px;
            text-align: center;
            min-height: 300px;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
        }

        .activity-display {
            flex-grow: 1;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.3rem;
            line-height: 1.8;
            margin-bottom: 30px;
        }

        .activity-controls {
            display: flex;
            gap: 15px;
            justify-content: center;
        }

        .btn {
            padding: 12px 30px;
            border: none;
            border-radius: 8px;
            font-size: 1rem;
            cursor: pointer;
            transition: all 0.3s ease;
            font-weight: 500;
        }

        .btn-primary {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
        }

        .btn-primary:hover {
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(102, 126, 234, 0.4);
        }

        .btn-secondary {
            background: #f0f0f0;
            color: #333;
        }

        .btn-secondary:hover {
            background: #e0e0e0;
        }

        footer {
            text-align: center;
            margin-top: 40px;
            color: white;
            opacity: 0.8;
        }

        .mood-options {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
            gap: 15px;
            margin: 20px 0;
        }

        .mood-option {
            padding: 20px;
            background: white;
            border: 2px solid #e0e0e0;
            border-radius: 12px;
            cursor: pointer;
            transition: all 0.3s ease;
            text-align: center;
        }

        .mood-option:hover {
            border-color: #667eea;
            transform: scale(1.05);
        }

        .mood-option.selected {
            border-color: #667eea;
            background: #f0f4ff;
        }

        .mood-emoji {
            font-size: 2rem;
            margin-bottom: 5px;
        }

        .hidden {
            display: none;
        }

        @media (max-width: 768px) {
            .container {
                padding: 15px;
            }
            
            header h1 {
                font-size: 2rem;
            }
            
            .activity-grid {
                grid-template-columns: 1fr;
            }
            
            .activity-card {
                padding: 20px;
            }
            
            .card {
                padding: 20px;
            }
            
            .activity-header {
                flex-direction: column;
                align-items: flex-start;
            }
            
            .back-btn {
                margin-bottom: 15px;
                margin-right: 0;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <h1>🧊 Team Icebreakers</h1>
            <p>Get your retrospective started with engaging activities</p>
        </header>

        <main>
            <div class="activity-selector" id="activity-selector">
                <h2>Choose an Icebreaker Activity</h2>
                <div class="activity-grid">
                    <div class="activity-card" data-activity="questions">
                        <div class="activity-icon">❓</div>
                        <h3>Random Questions</h3>
                        <p>Thought-provoking questions to spark conversation</p>
                    </div>
                    
                    <div class="activity-card" data-activity="would-you-rather">
                        <div class="activity-icon">🤔</div>
                        <h3>Would You Rather</h3>
                        <p>Fun dilemmas to get everyone thinking</p>
                    </div>
                    
                    <div class="activity-card" data-activity="mood-check">
                        <div class="activity-icon">😊</div>
                        <h3>Mood Check-in</h3>
                        <p>Share how you're feeling today</p>
                    </div>
                    
                    <div class="activity-card" data-activity="two-truths">
                        <div class="activity-icon">🎭</div>
                        <h3>Two Truths & a Lie</h3>
                        <p>Classic game to learn about teammates</p>
                    </div>
                    
                    <div class="activity-card" data-activity="word-association">
                        <div class="activity-icon">💭</div>
                        <h3>Word Association</h3>
                        <p>Quick word games to energize the team</p>
                    </div>
                    
                    <div class="activity-card" data-activity="gratitude">
                        <div class="activity-icon">🙏</div>
                        <h3>Gratitude Circle</h3>
                        <p>Share something you're grateful for</p>
                    </div>
                </div>
            </div>

            <div class="activity-content hidden" id="activity-content">
                <div class="activity-header">
                    <button class="back-btn" id="back-btn">← Back to Activities</button>
                    <h2 id="activity-title"></h2>
                </div>
                
                <div class="activity-body">
                    <div class="card" id="content-card">
                        <div class="activity-display" id="activity-display"></div>
                        <div class="activity-controls">
                            <button class="btn btn-primary" id="next-btn">Next</button>
                            <button class="btn btn-secondary" id="shuffle-btn">Shuffle</button>
                        </div>
                    </div>
                </div>
            </div>
        </main>

        <footer>
            <p>Perfect for team retrospectives, stand-ups, and team building sessions</p>
        </footer>
    </div>

    <script>
        // Icebreaker data
        const icebreakers = {
            questions: [
                "If you could have dinner with any historical figure, who would it be and why?",
                "What's the most interesting place you've ever visited?",
                "If you could learn any skill instantly, what would it be?",
                "What's your favorite way to spend a weekend?",
                "If you could time travel, would you go to the past or future?",
                "What's the best piece of advice you've ever received?",
                "If you could have any superpower, what would it be?",
                "What's your favorite childhood memory?",
                "If you could live anywhere in the world, where would it be?",
                "What's something you're really proud of?",
                "If you could master any instrument, which one would you choose?",
                "What's the most adventurous thing you've ever done?",
                "If you could have coffee with anyone (living or dead), who would it be?",
                "What's your favorite season and why?",
                "If you could switch lives with anyone for a day, who would it be?",
                "What's a skill you wish you had learned as a child?",
                "If you could eliminate one thing from your daily routine, what would it be?",
                "What's the most unusual food you've ever tried?",
                "If you could witness any event in history, what would it be?",
                "What's your go-to karaoke song?"
            ],
            
            "would-you-rather": [
                "Would you rather have the ability to fly or be invisible?",
                "Would you rather always be 10 minutes late or 20 minutes early?",
                "Would you rather have unlimited money or unlimited time?",
                "Would you rather be able to speak all languages or talk to animals?",
                "Would you rather live in the mountains or by the ocean?",
                "Would you rather have the power to read minds or predict the future?",
                "Would you rather never have to sleep or never have to eat?",
                "Would you rather be famous or be the best friend of someone famous?",
                "Would you rather have a rewind button or a pause button for your life?",
                "Would you rather always know when someone is lying or always get away with lying?",
                "Would you rather have a personal chef or a personal trainer?",
                "Would you rather be able to control fire or water?",
                "Would you rather live without music or without movies?",
                "Would you rather have a photographic memory or be able to forget anything you want?",
                "Would you rather be the smartest person in the room or the funniest?",
                "Would you rather work from home forever or never work from home again?",
                "Would you rather have free Wi-Fi wherever you go or free coffee wherever you go?",
                "Would you rather be able to teleport anywhere or be able to time travel?",
                "Would you rather always have to sing instead of speak or dance everywhere you go?",
                "Would you rather have the ability to change the past or see into the future?"
            ],
            
            "mood-check": [
                "How are you feeling right now? Share your current mood and energy level.",
                "What's one word that describes your mood today?",
                "On a scale of 1-10, how motivated are you feeling right now?",
                "What's bringing you joy today?",
                "How are you feeling about the work week ahead?",
                "What's your energy level like today?",
                "Share something that's on your mind right now.",
                "How are you feeling about our team's recent progress?",
                "What's your stress level today and what's causing it?",
                "What's one thing that would improve your mood right now?",
                "How connected do you feel to the team today?",
                "What's your confidence level for today's tasks?",
                "How are you feeling about work-life balance lately?",
                "What's your excitement level for upcoming projects?",
                "How supported do you feel by the team right now?"
            ],
            
            "two-truths": [
                "Share two truths and one lie about your childhood.",
                "Tell us two truths and one lie about your hobbies.",
                "Share two truths and one lie about places you've traveled.",
                "Tell us two truths and one lie about your family.",
                "Share two truths and one lie about your career journey.",
                "Tell us two truths and one lie about your favorite foods.",
                "Share two truths and one lie about your bucket list.",
                "Tell us two truths and one lie about your pets or animals you've encountered.",
                "Share two truths and one lie about your talents or skills.",
                "Tell us two truths and one lie about your favorite movies or books.",
                "Share two truths and one lie about your weekend activities.",
                "Tell us two truths and one lie about your educational background.",
                "Share two truths and one lie about your dream jobs.",
                "Tell us two truths and one lie about your biggest fears.",
                "Share two truths and one lie about your proudest moments."
            ],
            
            "word-association": [
                "Say the first word that comes to mind when you hear: 'Adventure'",
                "What's the first word you think of when you hear: 'Success'?",
                "Quick! First word that comes to mind: 'Teamwork'",
                "What word immediately comes to mind when you hear: 'Innovation'?",
                "First word association with: 'Challenge'",
                "What's your immediate word association with: 'Growth'?",
                "Quick response - first word for: 'Creativity'",
                "What word comes to mind when you hear: 'Leadership'?",
                "First word association: 'Future'",
                "What's the first word you think of with: 'Collaboration'?",
                "Quick! First word for: 'Change'",
                "What word immediately comes to mind: 'Learning'?",
                "First association with the word: 'Communication'",
                "What's your first thought when you hear: 'Problem-solving'?",
                "Quick word association with: 'Motivation'",
                "First word that comes to mind: 'Balance'",
                "What do you think of when you hear: 'Opportunity'?",
                "Quick association with: 'Trust'",
                "First word for: 'Flexibility'",
                "What comes to mind with: 'Achievement'?"
            ],
            
            gratitude: [
                "Share something you're grateful for today.",
                "What's one thing about your team that you appreciate?",
                "Tell us about someone who made your week better.",
                "What's a recent accomplishment you're thankful for?",
                "Share something in your personal life you're grateful for.",
                "What's a skill or ability you're thankful to have?",
                "Tell us about a challenge that taught you something valuable.",
                "What's something about your work that you appreciate?",
                "Share a moment from this week that made you smile.",
                "What's one thing about your current project you're grateful for?",
                "Tell us about a piece of feedback that helped you grow.",
                "What's something about your workspace or tools you appreciate?",
                "Share something you're looking forward to.",
                "What's a tradition or routine you're grateful for?",
                "Tell us about a lesson learned that you're thankful for.",
                "What's a relationship in your life you're grateful for?",
                "Share a technology or tool that makes your life easier.",
                "What's a personal strength you're thankful for?",
                "Tell us about a mentor or teacher who influenced you.",
                "What's something about your health you're grateful for?"
            ]
        };

        // Current activity state
        let currentActivity = null;
        let currentIndex = 0;
        let shuffledContent = [];

        // DOM elements
        const activitySelector = document.getElementById('activity-selector');
        const activityContent = document.getElementById('activity-content');
        const activityTitle = document.getElementById('activity-title');
        const activityDisplay = document.getElementById('activity-display');
        const backBtn = document.getElementById('back-btn');
        const nextBtn = document.getElementById('next-btn');
        const shuffleBtn = document.getElementById('shuffle-btn');

        // Event listeners
        document.addEventListener('DOMContentLoaded', function() {
            // Activity card clicks
            document.querySelectorAll('.activity-card').forEach(card => {
                card.addEventListener('click', function() {
                    const activity = this.dataset.activity;
                    startActivity(activity);
                });
            });

            // Back button
            backBtn.addEventListener('click', function() {
                showActivitySelector();
            });

            // Next button
            nextBtn.addEventListener('click', function() {
                showNextContent();
            });

            // Shuffle button
            shuffleBtn.addEventListener('click', function() {
                shuffleContent();
                currentIndex = 0;
                showCurrentContent();
            });
        });

        function startActivity(activityType) {
            currentActivity = activityType;
            currentIndex = 0;
            
            // Set title
            const titles = {
                'questions': 'Random Questions',
                'would-you-rather': 'Would You Rather',
                'mood-check': 'Mood Check-in',
                'two-truths': 'Two Truths & a Lie',
                'word-association': 'Word Association',
                'gratitude': 'Gratitude Circle'
            };
            
            activityTitle.textContent = titles[activityType];
            
            // Shuffle content
            shuffleContent();
            
            // Show activity content
            showActivityContent();
            showCurrentContent();
        }

        function shuffleContent() {
            const content = [...icebreakers[currentActivity]];
            shuffledContent = content.sort(() => Math.random() - 0.5);
        }

        function showCurrentContent() {
            if (currentActivity === 'mood-check' && currentIndex === 0) {
                showMoodCheckInterface();
            } else {
                activityDisplay.innerHTML = `<div style="font-size: 1.2em; max-width: 600px; text-align: center;">${shuffledContent[currentIndex]}</div>`;
            }
        }

        function showMoodCheckInterface() {
            const moods = [
                { emoji: '😊', label: 'Happy' },
                { emoji: '😔', label: 'Sad' },
                { emoji: '😴', label: 'Tired' },
                { emoji: '😤', label: 'Frustrated' },
                { emoji: '🤔', label: 'Thoughtful' },
                { emoji: '😌', label: 'Calm' },
                { emoji: '🤩', label: 'Excited' },
                { emoji: '😰', label: 'Anxious' },
                { emoji: '😎', label: 'Confident' },
                { emoji: '🥱', label: 'Bored' }
            ];

            let moodHtml = '<div style="margin-bottom: 20px; font-size: 1.2em;">How are you feeling right now?</div>';
            moodHtml += '<div class="mood-options">';
            
            moods.forEach(mood => {
                moodHtml += `
                    <div class="mood-option" onclick="selectMood('${mood.label}')">
                        <div class="mood-emoji">${mood.emoji}</div>
                        <div>${mood.label}</div>
                    </div>
                `;
            });
            
            moodHtml += '</div>';
            moodHtml += '<div style="margin-top: 20px; font-style: italic; color: #666; font-size: 0.9em;">Click on a mood to share with your team, then click Next for more check-in questions.</div>';
            
            activityDisplay.innerHTML = moodHtml;
        }

        function selectMood(mood) {
            // Remove previous selection
            document.querySelectorAll('.mood-option').forEach(option => {
                option.classList.remove('selected');
            });
            
            // Add selection to clicked mood
            event.target.closest('.mood-option').classList.add('selected');
            
            // Show selected mood message
            setTimeout(() => {
                activityDisplay.innerHTML = `<div style="font-size: 1.3em; text-align: center;">Thanks for sharing! You're feeling <strong>${mood}</strong> today. 🎉<br><br><div style="font-size: 0.9em; color: #666; margin-top: 15px;">Click Next to continue with more check-in questions.</div></div>`;
            }, 1000);
        }

        function showNextContent() {
            currentIndex = (currentIndex + 1) % shuffledContent.length;
            showCurrentContent();
        }

        function showActivitySelector() {
            activitySelector.classList.remove('hidden');
            activityContent.classList.add('hidden');
        }

        function showActivityContent() {
            activitySelector.classList.add('hidden');
            activityContent.classList.remove('hidden');
        }

        // Add some animation effects
        function addClickEffect(element) {
            element.style.transform = 'scale(0.95)';
            setTimeout(() => {
                element.style.transform = 'scale(1)';
            }, 150);
        }

        // Add click effects to buttons
        document.addEventListener('click', function(e) {
            if (e.target.classList.contains('btn') || e.target.classList.contains('activity-card')) {
                addClickEffect(e.target);
            }
        });

        // Keyboard navigation
        document.addEventListener('keydown', function(e) {
            if (activityContent.classList.contains('hidden')) return;
            
            if (e.key === 'ArrowRight' || e.key === ' ') {
                e.preventDefault();
                showNextContent();
            } else if (e.key === 'ArrowLeft') {
                e.preventDefault();
                currentIndex = currentIndex > 0 ? currentIndex - 1 : shuffledContent.length - 1;
                showCurrentContent();
            } else if (e.key === 'Escape') {
                showActivitySelector();
            }
        });
    </script>
</body>
</html>
```

## Usage Tips

### For Facilitators
- **Start with lighter activities** like "Random Questions" or "Would You Rather" to warm up the team
- **Use "Mood Check-in"** at the beginning of retrospectives to gauge team sentiment
- **Try "Gratitude Circle"** to end on a positive note
- **Mix activities** throughout longer sessions to maintain engagement

### For Remote Teams
- **Screen share** the application during video calls
- **Take turns** reading questions aloud
- **Use breakout rooms** for smaller group discussions
- **Follow up** with team chat for continued conversation

### Customization
- **Add your own questions** by editing the JavaScript arrays
- **Modify colors** by changing the CSS gradient and color values
- **Add new activities** by extending the icebreakers object
- **Adjust timing** by modifying animation durations

## Technical Details

- **Pure HTML/CSS/JavaScript** - No external dependencies
- **Responsive design** - Works on desktop, tablet, and mobile
- **Modern browser support** - Uses CSS Grid and Flexbox
- **Lightweight** - Single file under 50KB
- **Offline capable** - Works without internet connection

## Keyboard Shortcuts

- **Right Arrow / Space** - Next question
- **Left Arrow** - Previous question  
- **Escape** - Return to main menu

Enjoy building stronger team connections with these icebreaker activities! 🎉