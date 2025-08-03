# lotm-beyonder-system
A fun and simple page created as a tribute to LOTM, you are free to enhance any cool features to it as you please.
/* hence I provide the instructions and sourcecode for your refference. */

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Lord of the Mysteries - Beyonder System</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Cinzel:wght@400;500;600;700&family=Crimson+Text:ital,wght@0,400;0,600;1,400&display=swap');
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Crimson Text', serif;
            background: #0a0a0f;
            color: #e8e3d6;
            line-height: 1.6;
            overflow-x: hidden;
            min-height: 100vh;
            position: relative;
        }
        
        /* Animated background */
        body::before {
            content: '';
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: 
                radial-gradient(circle at 20% 50%, rgba(120, 70, 180, 0.1) 0%, transparent 50%),
                radial-gradient(circle at 80% 20%, rgba(180, 120, 70, 0.08) 0%, transparent 50%),
                radial-gradient(circle at 40% 80%, rgba(70, 120, 180, 0.06) 0%, transparent 50%),
                linear-gradient(135deg, #0a0a0f 0%, #1a1520 50%, #2a1f30 100%);
            z-index: -2;
            animation: mysticalAura 20s ease-in-out infinite alternate;
        }
        
        /* Floating particles */
        .particles {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: -1;
        }
        
        .particle {
            position: absolute;
            width: 2px;
            height: 2px;
            background: rgba(180, 140, 70, 0.6);
            border-radius: 50%;
            animation: float 15s infinite linear;
        }
        
        @keyframes mysticalAura {
            0% { transform: scale(1) rotate(0deg); }
            100% { transform: scale(1.05) rotate(2deg); }
        }
        
        @keyframes float {
            0% {
                transform: translateY(100vh) rotate(0deg);
                opacity: 0;
            }
            10% {
                opacity: 1;
            }
            90% {
                opacity: 1;
            }
            100% {
                transform: translateY(-100px) rotate(360deg);
                opacity: 0;
            }
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
            position: relative;
            z-index: 1;
        }
        
        /* Header */
        .header {
            text-align: center;
            padding: 40px 0;
            background: linear-gradient(135deg, rgba(30, 20, 40, 0.8) 0%, rgba(50, 30, 60, 0.6) 100%);
            border-bottom: 2px solid rgba(180, 140, 70, 0.3);
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.5);
            backdrop-filter: blur(10px);
        }
        
        .title {
            font-family: 'Cinzel', serif;
            font-size: 3.5rem;
            font-weight: 700;
            color: #f4d03f;
            text-shadow: 
                0 0 10px rgba(244, 208, 63, 0.5),
                0 0 20px rgba(244, 208, 63, 0.3),
                0 0 30px rgba(244, 208, 63, 0.2);
            margin-bottom: 10px;
            animation: titleGlow 3s ease-in-out infinite alternate;
        }
        
        @keyframes titleGlow {
            0% { text-shadow: 0 0 10px rgba(244, 208, 63, 0.5), 0 0 20px rgba(244, 208, 63, 0.3); }
            100% { text-shadow: 0 0 15px rgba(244, 208, 63, 0.8), 0 0 25px rgba(244, 208, 63, 0.5); }
        }
        
        .subtitle {
            font-size: 1.4rem;
            color: #c39bd3;
            font-style: italic;
            margin-bottom: 20px;
        }
        
        /* Story Section */
        .story-section {
            background: linear-gradient(135deg, rgba(20, 15, 30, 0.9) 0%, rgba(30, 20, 40, 0.8) 100%);
            border: 1px solid rgba(180, 140, 70, 0.2);
            border-radius: 15px;
            padding: 40px;
            margin: 40px 0;
            box-shadow: 
                0 8px 32px rgba(0, 0, 0, 0.4),
                inset 0 1px 0 rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(15px);
        }
        
        .section-title {
            font-family: 'Cinzel', serif;
            font-size: 2.2rem;
            color: #f4d03f;
            margin-bottom: 20px;
            text-align: center;
            position: relative;
        }
        
        .section-title::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 100px;
            height: 2px;
            background: linear-gradient(90deg, transparent, #f4d03f, transparent);
        }
        
        .story-text {
            font-size: 1.2rem;
            line-height: 1.8;
            color: #e8e3d6;
            text-align: justify;
            margin-bottom: 20px;
        }
        
        .highlight {
            color: #f4d03f;
            font-weight: 600;
        }
        
        /* Game Section */
        .game-section {
            background: linear-gradient(135deg, rgba(15, 10, 25, 0.95) 0%, rgba(25, 15, 35, 0.9) 100%);
            border: 2px solid rgba(180, 140, 70, 0.3);
            border-radius: 20px;
            padding: 40px;
            margin: 40px 0;
            box-shadow: 
                0 12px 40px rgba(0, 0, 0, 0.6),
                inset 0 1px 0 rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(20px);
        }
        
        .input-group {
            margin-bottom: 25px;
        }
        
        .input-label {
            display: block;
            font-family: 'Cinzel', serif;
            font-size: 1.1rem;
            color: #f4d03f;
            margin-bottom: 8px;
            font-weight: 500;
        }
        
        .input-field, .select-field {
            width: 100%;
            padding: 12px 16px;
            background: rgba(10, 5, 20, 0.8);
            border: 2px solid rgba(180, 140, 70, 0.4);
            border-radius: 8px;
            color: #e8e3d6;
            font-size: 1rem;
            font-family: 'Crimson Text', serif;
            transition: all 0.3s ease;
        }
        
        .input-field:focus, .select-field:focus {
            outline: none;
            border-color: #f4d03f;
            box-shadow: 0 0 15px rgba(244, 208, 63, 0.3);
            background: rgba(15, 10, 25, 0.9);
        }
        
        .select-field option {
            background: #1a1520;
            color: #e8e3d6;
            padding: 10px;
        }
        
        .generate-btn {
            width: 100%;
            padding: 15px;
            background: linear-gradient(135deg, #8e44ad, #9b59b6);
            border: none;
            border-radius: 10px;
            color: white;
            font-family: 'Cinzel', serif;
            font-size: 1.2rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            text-transform: uppercase;
            letter-spacing: 1px;
            box-shadow: 0 4px 15px rgba(142, 68, 173, 0.4);
        }
        
        .generate-btn:hover {
            background: linear-gradient(135deg, #9b59b6, #af7ac5);
            transform: translateY(-2px);
            box-shadow: 0 6px 25px rgba(142, 68, 173, 0.6);
        }
        
        .generate-btn:active {
            transform: translateY(0);
        }
        
        /* Results Section */
        .results-section {
            background: linear-gradient(135deg, rgba(10, 5, 20, 0.95) 0%, rgba(20, 10, 30, 0.9) 100%);
            border: 2px solid rgba(244, 208, 63, 0.4);
            border-radius: 15px;
            padding: 30px;
            margin-top: 30px;
            display: none;
            box-shadow: 
                0 8px 32px rgba(0, 0, 0, 0.6),
                inset 0 1px 0 rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(15px);
        }
        
        .results-section.show {
            display: block;
            animation: fadeInUp 0.6s ease-out;
        }
        
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        .result-item {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 12px 0;
            border-bottom: 1px solid rgba(180, 140, 70, 0.2);
        }
        
        .result-item:last-child {
            border-bottom: none;
        }
        
        .result-label {
            font-family: 'Cinzel', serif;
            font-weight: 500;
            color: #f4d03f;
            min-width: 150px;
        }
        
        .result-value {
            color: #e8e3d6;
            text-align: right;
            flex: 1;
        }
        
        .abilities-list {
            background: rgba(5, 0, 15, 0.6);
            border: 1px solid rgba(180, 140, 70, 0.3);
            border-radius: 10px;
            padding: 20px;
            margin-top: 20px;
        }
        
        .abilities-title {
            font-family: 'Cinzel', serif;
            color: #f4d03f;
            font-size: 1.3rem;
            margin-bottom: 15px;
            text-align: center;
        }
        
        .ability-item {
            background: rgba(30, 20, 40, 0.4);
            border: 1px solid rgba(180, 140, 70, 0.2);
            border-radius: 6px;
            padding: 10px 15px;
            margin: 8px 0;
            color: #e8e3d6;
            transition: all 0.3s ease;
        }
        
        .ability-item:hover {
            background: rgba(40, 30, 50, 0.6);
            border-color: rgba(244, 208, 63, 0.4);
            transform: translateX(5px);
        }
        
        .pathway-tree {
            background: rgba(0, 0, 10, 0.8);
            border: 1px solid rgba(180, 140, 70, 0.3);
            border-radius: 10px;
            padding: 20px;
            margin-top: 20px;
            font-family: 'Courier New', monospace;
            font-size: 0.9rem;
            white-space: pre-line;
            overflow-x: auto;
        }
        
        /* Responsive Design */
        @media (max-width: 768px) {
            .title {
                font-size: 2.5rem;
            }
            
            .container {
                padding: 0 15px;
            }
            
            .story-section, .game-section {
                padding: 25px;
            }
            
            .result-item {
                flex-direction: column;
                align-items: flex-start;
                gap: 5px;
            }
            
            .result-label {
                min-width: auto;
            }
        }
        
        /* Loading animation */
        .loading {
            text-align: center;
            padding: 20px;
            color: #f4d03f;
        }
        
        .loading::after {
            content: '...';
            animation: dots 1.5s steps(4, end) infinite;
        }
        
        @keyframes dots {
            0%, 20% { content: ''; }
            40% { content: '.'; }
            60% { content: '..'; }
            80%, 100% { content: '...'; }
        }
    </style>
</head>
<body>
    <!-- Floating particles -->
    <div class="particles" id="particles"></div>
    
    <div class="header">
        <div class="container">
            <h1 class="title">Lord of the Mysteries</h1>
            <p class="subtitle">Beyonder System Generator</p>
        </div>
    </div>
    
    <div class="container">
        <!-- Story Section -->
        <section class="story-section">
            <h2 class="section-title">The Mystical World Awaits</h2>
            <p class="story-text">
                In the fog-shrouded world of <span class="highlight">Lord of the Mysteries</span>, supernatural beings known as <span class="highlight">Beyonders</span> wield extraordinary powers through mysterious potions and ancient pathways. Each pathway represents a unique approach to transcendence, from the enigmatic <span class="highlight">Fool</span> who manipulates fate and probability, to the mighty <span class="highlight">Tyrant</span> who commands storms and seas.
            </p>
            <p class="story-text">
                The power system is built upon <span class="highlight">22 distinct pathways</span>, each containing <span class="highlight">10 sequences</span> from Sequence 9 (the lowest) to Sequence 0 (True God). As Beyonders advance through sequences by consuming higher-level potions, they gain increasingly powerful abilities but also face greater risks of losing control to the madness that comes with forbidden knowledge.
            </p>
            <p class="story-text">
                Your journey begins now. Choose your epoch, align with a church, select your pathway, and discover what mysteries await in the shadows...
            </p>
        </section>
        
        <!-- How to Play Section -->
        <section class="story-section">
            <h2 class="section-title">How to Forge Your Destiny</h2>
            <p class="story-text">
                <span class="highlight">Step 1:</span> Enter your Beyonder name - this will be your identity in the mystical world.
            </p>
            <p class="story-text">
                <span class="highlight">Step 2:</span> Choose your Epoch - each era offers different influences and power dynamics, from the chaotic Age of Creation to the modern Age of Iron and Steam.
            </p>
            <p class="story-text">
                <span class="highlight">Step 3:</span> Select your Church affiliation - align with divine organizations for support and resources, or remain independent for freedom.
            </p>
            <p class="story-text">
                <span class="highlight">Step 4:</span> Pick your Pathway - this determines your fundamental approach to supernatural power and the nature of your abilities.
            </p>
            <p class="story-text">
                <span class="highlight">Step 5:</span> Choose your Sequence level - higher sequences grant greater power but require more dangerous potions and deeper mysteries.
            </p>
            <p class="story-text">
                Once complete, witness your transformation into a true Beyonder with unique abilities, divine blessings, and a path toward godhood!
            </p>
        </section>
        
        <!-- Game Section -->
        <section class="game-section">
            <h2 class="section-title">Create Your Beyonder</h2>
            
            <form id="beyonderForm">
                <div class="input-group">
                    <label class="input-label" for="name">Beyonder Name</label>
                    <input type="text" id="name" class="input-field" placeholder="Enter your mystical identity..." required>
                </div>
                
                <div class="input-group">
                    <label class="input-label" for="epoch">Choose Your Epoch</label>
                    <select id="epoch" class="select-field" required>
                        <option value="">Select an Epoch...</option>
                        <option value="first">First Epoch - Age of Creation</option>
                        <option value="second">Second Epoch - Age of Darkness</option>
                        <option value="third">Third Epoch - Age of Catastrophe</option>
                        <option value="fourth">Fourth Epoch - Age of Gods</option>
                        <option value="fifth">Fifth Epoch - Age of Iron and Steam</option>
                    </select>
                </div>
                
                <div class="input-group">
                    <label class="input-label" for="church">Church Affiliation</label>
                    <select id="church" class="select-field" required>
                        <option value="">Choose your allegiance...</option>
                        <option value="evernight">Church of the Evernight Goddess</option>
                        <option value="storms">Church of the Lord of Storms</option>
                        <option value="sun">Church of the Eternal Blazing Sun</option>
                        <option value="earth">Church of the Earth Mother</option>
                        <option value="knowledge">Church of the God of Knowledge and Wisdom</option>
                        <option value="steam">Church of the God of Steam and Machinery</option>
                        <option value="combat">Church of the God of Combat</option>
                        <option value="none">Independent (No Church)</option>
                    </select>
                </div>
                
                <div class="input-group">
                    <label class="input-label" for="pathway">Mystical Pathway</label>
                    <select id="pathway" class="select-field" required>
                        <option value="">Select your path to power...</option>
                        <option value="fool">The Fool - Master of Fate and Probability</option>
                        <option value="tyrant">Tyrant - Lord of Storms and Seas</option>
                        <option value="visionary">Visionary - Manipulator of Dreams and Mind</option>
                        <option value="sun">Sun - Wielder of Light and Purification</option>
                        <option value="white_tower">White Tower - Seeker of Knowledge</option>
                        <option value="red_priest">Red Priest - Conqueror and Warmonger</option>
                        <option value="demoness">Demoness - Bringer of Catastrophe</option>
                        <option value="death">Death - Guardian of Spirits and Mortality</option>
                        <option value="mother">Mother - Nurture of Nature and Life</option>
                        <option value="moon">Moon - Master of Transformation</option>
                    </select>
                </div>
                
                <div class="input-group">
                    <label class="input-label" for="sequence">Sequence Level (Power Rank)</label>
                    <select id="sequence" class="select-field" required>
                        <option value="">Choose your current power level...</option>
                        <option value="9">Sequence 9 - Novice Beyonder</option>
                        <option value="8">Sequence 8 - Experienced Beyonder</option>
                        <option value="7">Sequence 7 - Veteran Beyonder</option>
                        <option value="6">Sequence 6 - Elite Beyonder</option>
                        <option value="5">Sequence 5 - Master Beyonder</option>
                        <option value="4">Sequence 4 - Demigod</option>
                        <option value="3">Sequence 3 - Saint</option>
                        <option value="2">Sequence 2 - Angel</option>
                        <option value="1">Sequence 1 - King of Angels</option>
                        <option value="0">Sequence 0 - True God</option>
                    </select>
                </div>
                
                <button type="submit" class="generate-btn">Forge Your Destiny</button>
            </form>
            
            <!-- Results Section -->
            <div class="results-section" id="results">
                <!-- Results will be populated by JavaScript -->
            </div>
        </section>
    </div>
    
    <script>
        // Beyonder System Data
        const pathwayData = {
            fool: {
                name: "The Fool",
                sequences: ["Fool", "Miracle Invoker", "Scholar of Yore", "Bizarro Sorcerer", "Marionettist", "Faceless", "Nimblewright Master", "Magician", "Clown", "Seer"],
                abilities: {
                    9: ["Spiritual Vision", "Divination", "Danger Premonition", "Spirit World Perception"],
                    8: ["Enhanced Agility", "Paper Figurine Substitutes", "Flame Jumping", "Acrobatic Mastery"],
                    7: ["Illusion Creation", "Air Bullets", "Flame Control", "Sleight of Hand Mastery"],
                    6: ["Puppet Creation", "Thread Control", "Enhanced Manipulation", "Marionette Dancing"],
                    5: ["Face Changing", "Body Morphing", "Identity Theft", "Perfect Disguise"],
                    4: ["Marionette Control", "Spirit Body Threads", "Mass Manipulation", "Puppet Master Authority"],
                    3: ["Bizarre Magic", "Reality Distortion", "Luck Manipulation", "Chaos Induction"],
                    2: ["Historical Projection", "Time Manipulation", "Ancient Knowledge", "Scholar's Wisdom"],
                    1: ["Miracle Invocation", "Fate Control", "Divine Authority", "Reality Rewriting"],
                    0: ["Omniscience", "Universal Authority", "Absolute Control", "Creator's Will"]
                },
                description: "Masters of fate, probability, and the mysterious. They manipulate luck, create illusions, and eventually gain the power to rewrite reality itself."
            },
            tyrant: {
                name: "Tyrant",
                sequences: ["Tyrant", "Weather Warlock", "Sea King", "Ocean Songster", "Thunder God", "Tyrant", "Wind-blessed", "Seafarer", "Folk of Rage", "Sailor"],
                abilities: {
                    9: ["Enhanced Swimming", "Water Walking", "Storm Resistance", "Sea Navigation"],
                    8: ["Berserk State", "Enhanced Strength", "Rage Amplification", "Combat Fury"],
                    7: ["Wind Control", "Weather Prediction", "Sea Navigation", "Storm Calling"],
                    6: ["Lightning Control", "Storm Summoning", "Wind Blessing", "Atmospheric Manipulation"],
                    5: ["Sea Control", "Tsunami Creation", "Ocean Authority", "Maritime Dominion"],
                    4: ["Thunder God Powers", "Divine Lightning", "Storm Domain", "Celestial Wrath"],
                    3: ["Ocean Songs", "Sea Creature Control", "Water Mastery", "Aquatic Symphony"],
                    2: ["Sea Dominion", "Naval Authority", "Ocean King Powers", "Maritime Supremacy"],
                    1: ["Weather Control", "Storm Authority", "Natural Disaster Control", "Atmospheric Dominion"],
                    0: ["Absolute Storm Control", "Natural Authority", "Calamity Dominion", "Elemental Supremacy"]
                },
                description: "Lords of storms, seas, and natural disasters. They command the fury of nature and wield the power of elemental destruction."
            },
            visionary: {
                name: "Visionary",
                sequences: ["Visionary", "Author", "Manipulator", "Nightmare", "Dreamwalker", "Psychologist", "Hypnotist", "Psychoanalyst", "Psychiatrist", "Spectator"],
                abilities: {
                    9: ["Psychological Analysis", "Emotion Reading", "Mental Observation", "Behavior Study"],
                    8: ["Mental Treatment", "Psychological Therapy", "Mind Reading", "Emotional Healing"],
                    7: ["Psychological Analysis", "Behavior Prediction", "Mental Mapping", "Pattern Recognition"],
                    6: ["Hypnosis", "Mental Suggestion", "Consciousness Control", "Mind Manipulation"],
                    5: ["Psychology Mastery", "Mental Manipulation", "Behavioral Control", "Psychic Influence"],
                    4: ["Dream Walking", "Nightmare Creation", "Subconscious Control", "Mental Realm Access"],
                    3: ["Mental Projection", "Fear Manifestation", "Dream Control", "Psychological Warfare"],
                    2: ["Mind Control", "Mental Domination", "Consciousness Manipulation", "Psychic Authority"],
                    1: ["Reality Writing", "Concept Creation", "Universal Storytelling", "Narrative Control"],
                    0: ["Omniscient Vision", "Reality Control", "Universal Consciousness", "Absolute Awareness"]
                },
                description: "Masters of the mind and consciousness. They manipulate dreams, control thoughts, and eventually gain the power to rewrite reality through storytelling."
            },
            sun: {
                name: "Sun",
                sequences: ["Sun", "Prince of Abolition", "Angel of Imagination", "Rector", "Dawn Paladin", "Solar High Priest", "Priest of Light", "Notary", "Enlightened", "Bard"],
                abilities: {
                    9: ["Inspiring Songs", "Morale Boost", "Performance Magic", "Artistic Enhancement"],
                    8: ["Knowledge Seeking", "Learning Enhancement", "Wisdom Gain", "Intellectual Pursuit"],
                    7: ["Contract Magic", "Truth Binding", "Legal Authority", "Sacred Oaths"],
                    6: ["Light Magic", "Purification", "Divine Blessing", "Sacred Radiance"],
                    5: ["Solar Power", "Light Control", "Radiant Authority", "Divine Illumination"],
                    4: ["Dawn Powers", "Light Mastery", "Solar Blessing", "Morning Glory"],
                    3: ["Church Authority", "Divine Power", "Sacred Control", "Religious Dominion"],
                    2: ["Imagination Power", "Concept Creation", "Creative Authority", "Divine Inspiration"],
                    1: ["Abolition Power", "Destruction Authority", "Divine Negation", "Absolute Denial"],
                    0: ["Solar Dominion", "Light Authority", "Divine Sun Control", "Cosmic Radiance"]
                },
                description: "Wielders of light, purification, and divine authority. They bring illumination to darkness and possess the power to abolish evil."
            },
            white_tower: {
                name: "White Tower",
                sequences: ["White Tower", "Sage", "Scientist", "Warlock", "Lorekeeper", "Mysticologist", "Professor", "Librarian", "Erudite Scholar", "Reader"],
                abilities: {
                    9: ["Speed Reading", "Memory Enhancement", "Knowledge Absorption", "Learning Acceleration"],
                    8: ["Scholarly Expertise", "Research Mastery", "Academic Authority", "Intellectual Prowess"],
                    7: ["Knowledge Management", "Information Control", "Library Mastery", "Data Manipulation"],
                    6: ["Teaching Excellence", "Educational Authority", "Wisdom Sharing", "Knowledge Transfer"],
                    5: ["Mystical Research", "Occult Knowledge", "Supernatural Understanding", "Esoteric Mastery"],
                    4: ["Ancient Wisdom", "Lost Knowledge", "Historical Secrets", "Forbidden Lore"],
                    3: ["Arcane Mastery", "Magical Research", "Supernatural Science", "Mystical Authority"],
                    2: ["Scientific Transcendence", "Universal Understanding", "Cosmic Knowledge", "Reality Research"],
                    1: ["Infinite Wisdom", "Universal Truth", "Absolute Knowledge", "Omniscient Authority"],
                    0: ["Tower of Truth", "Knowledge Supremacy", "Universal Understanding", "Cosmic Wisdom"]
                },
                description: "Seekers of knowledge and truth. They pursue understanding of the universe's mysteries and gain power through accumulated wisdom."
            },
            red_priest: {
                name: "Red Priest",
                sequences: ["Red Priest", "Conqueror", "War Bishop", "Iron-blooded Knight", "Reaper", "Conspirator", "Pyromaniac", "Provoker", "Hunter"],
                abilities: {
                    9: ["Enhanced Tracking", "Prey Marking", "Survival Instincts", "Predator Awareness"],
                    8: ["Provocation Mastery", "Conflict Instigation", "Emotional Manipulation", "Chaos Creation"],
                    7: ["Fire Control", "Pyromania", "Destructive Flames", "Burning Passion"],
                    6: ["Strategic Planning", "Conspiracy Mastery", "Manipulation Schemes", "Political Intrigue"],
                    5: ["Death Dealing", "Soul Reaping", "Life Force Drain", "Mortality Control"],
                    4: ["Combat Mastery", "Warrior Authority", "Battle Excellence", "Military Leadership"],
                    3: ["War Authority", "Battle Control", "Military Command", "Strategic Supremacy"],
                    2: ["Conquest Power", "Territory Control", "Empire Building", "Absolute Command"],
                    1: ["Divine War Authority", "Ultimate Conquest", "Supreme Command", "Military Godhood"],
                    0: ["War Supremacy", "Absolute Conquest", "Universal Command", "Military Omnipotence"]
                },
                description: "Warriors and conquerors who thrive on conflict. They master the arts of war, strategy, and conquest to build empires."
            },
            demoness: {
                name: "Demoness",
                sequences: ["Primordial Demoness", "Demoness of Apocalypse", "Demoness of Disasters", "Demoness of Unaging", "Silent Disciple", "Despair", "Pleasure Witch", "Witch", "Instigator", "Assassin"],
                abilities: {
                    9: ["Stealth Mastery", "Silent Killing", "Shadow Movement", "Assassination Arts"],
                    8: ["Instigation Powers", "Conflict Creation", "Social Manipulation", "Chaos Seeding"],
                    7: ["Witchcraft", "Curse Magic", "Potion Brewing", "Hex Casting"],
                    6: ["Pleasure Manipulation", "Seduction Mastery", "Emotional Control", "Desire Amplification"],
                    5: ["Despair Induction", "Hope Crushing", "Mental Breakdown", "Psychological Destruction"],
                    4: ["Silence Powers", "Sound Negation", "Stealth Perfection", "Invisible Authority"],
                    3: ["Eternal Youth", "Age Control", "Beauty Mastery", "Time Resistance"],
                    2: ["Disaster Creation", "Catastrophe Control", "Calamity Summoning", "Destruction Authority"],
                    1: ["Apocalypse Powers", "End Times Control", "Ultimate Destruction", "World Ending Authority"],
                    0: ["Primordial Chaos", "Original Destruction", "Absolute Catastrophe", "Universal Ending"]
                },
                description: "Beings of catastrophe and seduction. They bring disasters, manipulate desires, and hold the power to end civilizations."
            },
            death: {
                name: "Death",
                sequences: ["Death", "Death Consul", "Underworld Emperor", "Pale Emperor", "Artificial Death", "Gatekeeper", "Spirit Guide", "Spirit Medium", "Gravedigger", "Corpse Collector"],
                abilities: {
                    9: ["Corpse Handling", "Death Sense", "Undead Detection", "Spiritual Awareness"],
                    8: ["Grave Digging", "Burial Rites", "Death Preparation", "Corpse Preservation"],
                    7: ["Spirit Communication", "Ghost Contact", "Séance Mastery", "Ethereal Bridge"],
                    6: ["Spirit Guidance", "Soul Navigation", "Afterlife Knowledge", "Death Counseling"],
                    5: ["Gate Control", "Portal Creation", "Dimensional Access", "Boundary Management"],
                    4: ["Artificial Death", "False Mortality", "Death Simulation", "Life Force Control"],
                    3: ["Pale Dominion", "Death Mastery", "Mortality Control", "Life/Death Balance"],
                    2: ["Underworld Authority", "Death Realm Control", "Soul Dominion", "Afterlife Mastery"],
                    1: ["Death Consultation", "Universal Mortality", "Absolute Death Control", "Soul Supremacy"],
                    0: ["Death Incarnate", "Mortality Absolute", "Universal Death Authority", "Cosmic Finality"]
                },
                description: "Guardians of the boundary between life and death. They commune with spirits and command the forces of mortality."
            },
            mother: {
                name: "Mother",
                sequences: ["Mother", "Life School Dean", "Harvest Goddess", "Beauty Goddess", "Moon Apostle", "Druid", "Shaman", "Harvest Priest", "Beast Tamer", "Planter"],
                abilities: {
                    9: ["Plant Growth", "Agricultural Mastery", "Crop Enhancement", "Botanical Knowledge"],
                    8: ["Animal Taming", "Beast Communication", "Creature Control", "Wildlife Mastery"],
                    7: ["Harvest Blessing", "Fertility Enhancement", "Seasonal Control", "Agricultural Authority"],
                    6: ["Shamanic Powers", "Nature Communion", "Tribal Leadership", "Spiritual Guidance"],
                    5: ["Druidic Magic", "Natural Harmony", "Forest Control", "Elemental Balance"],
                    4: ["Lunar Powers", "Moon Blessing", "Tidal Control", "Nocturnal Authority"],
                    3: ["Beauty Perfection", "Aesthetic Control", "Attraction Mastery", "Visual Dominion"],
                    2: ["Harvest Supremacy", "Agricultural Godhood", "Fertility Authority", "Life Creation"],
                    1: ["Life Education", "Universal Knowledge", "Wisdom Teaching", "Cosmic Understanding"],
                    0: ["Mother of All", "Life Origin", "Universal Nurturing", "Creation Authority"]
                },
                description: "Nurturers of life and nature. They command the forces of growth, fertility, and the natural world."
            },
            moon: {
                name: "Moon",
                sequences: ["Moon", "Life School Dean", "Harvest Goddess", "Beauty Goddess", "Potions Professor", "Werewolf", "Potions Professor", "Vampire", "Beast Tamer", "Apothecary"],
                abilities: {
                    9: ["Potion Brewing", "Herbal Knowledge", "Medicinal Mastery", "Alchemical Basics"],
                    8: ["Beast Transformation", "Animal Forms", "Creature Control", "Shapeshifting"],
                    7: ["Vampiric Powers", "Blood Control", "Life Drain", "Immortal Traits"],
                    6: ["Advanced Potions", "Magical Brewing", "Elixir Creation", "Alchemical Mastery"],
                    5: ["Lycanthrope Form", "Wolf Transformation", "Pack Leadership", "Predator Instincts"],
                    4: ["Potion Mastery", "Teaching Authority", "Alchemical Expertise", "Formula Creation"],
                    3: ["Beauty Incarnate", "Perfect Form", "Attraction Control", "Aesthetic Authority"],
                    2: ["Harvest Mastery", "Life Control", "Growth Authority", "Natural Dominion"],
                    1: ["Life Education", "Universal Teaching", "Wisdom Authority", "Knowledge Supremacy"],
                    0: ["Lunar Supremacy", "Transformation Master", "Cycle Control", "Cosmic Change"]
                },
                description: "Masters of transformation and lunar mysteries. They control change, metamorphosis, and the cycles of existence."
            }
        };

        const epochData = {
            first: {
                name: "First Epoch - Age of Creation",
                influence: "Ancient powers are more accessible, but knowledge is fragmented and dangerous.",
                bonus: "Enhanced connection to primordial forces"
            },
            second: {
                name: "Second Epoch - Age of Darkness",
                influence: "Dark and chaotic energies enhance destructive abilities.",
                bonus: "Increased power from shadows and corruption"
            },
            third: {
                name: "Third Epoch - Age of Catastrophe",
                influence: "Catastrophic events amplify disaster-related powers.",
                bonus: "Enhanced destructive and chaotic abilities"
            },
            fourth: {
                name: "Fourth Epoch - Age of Gods",
                influence: "Divine authorities are stronger, but more restrictive.",
                bonus: "Amplified divine connections and restrictions"
            },
            fifth: {
                name: "Fifth Epoch - Age of Iron and Steam",
                influence: "Technology and mysticism blend, offering hybrid abilities.",
                bonus: "Enhanced technological integration"
            }
        };

        const churchData = {
            evernight: {
                name: "Church of the Evernight Goddess",
                benefits: "Enhanced stealth abilities and dream-related powers",
                authority: "Goddess of Night and Dreams"
            },
            storms: {
                name: "Church of the Lord of Storms",
                benefits: "Amplified storm and weather control abilities",
                authority: "Lord of Storms and Lightning"
            },
            sun: {
                name: "Church of the Eternal Blazing Sun",
                benefits: "Strengthened light and purification powers",
                authority: "Eternal Blazing Sun"
            },
            earth: {
                name: "Church of the Earth Mother",
                benefits: "Enhanced nature and harvest-related abilities",
                authority: "Earth Mother and Fertility"
            },
            knowledge: {
                name: "Church of the God of Knowledge and Wisdom",
                benefits: "Accelerated learning and enhanced analytical abilities",
                authority: "God of Knowledge and Wisdom"
            },
            steam: {
                name: "Church of the God of Steam and Machinery",
                benefits: "Improved technology integration and mechanical abilities",
                authority: "God of Steam and Machinery"
            },
            combat: {
                name: "Church of the God of Combat",
                benefits: "Enhanced combat prowess and strategic thinking",
                authority: "God of Combat and War"
            },
            none: {
                name: "Independent (No Church)",
                benefits: "Freedom from church restrictions but lack of divine support",
                authority: "Self-Reliant Path"
            }
        };

        // Create floating particles
        function createParticles() {
            const particlesContainer = document.getElementById('particles');
            const particleCount = 50;

            for (let i = 0; i < particleCount; i++) {
                const particle = document.createElement('div');
                particle.className = 'particle';
                particle.style.left = Math.random() * 100 + '%';
                particle.style.animationDelay = Math.random() * 15 + 's';
                particle.style.animationDuration = (15 + Math.random() * 10) + 's';
                particlesContainer.appendChild(particle);
            }
        }

        // Get sequence class
        function getSequenceClass(sequence) {
            const seq = parseInt(sequence);
            if (seq >= 7) return "Low Sequence";
            else if (seq >= 4) return "Mid Sequence";
            else if (seq >= 2) return "High Sequence";
            else if (seq === 1) return "Angel/King of Angels";
            else return "True God";
        }

        // Generate pathway advancement tree
        function generatePathwayTree(pathway) {
            const data = pathwayData[pathway];
            let tree = `═══ ${data.name.toUpperCase()} PATHWAY ADVANCEMENT TREE ═══\n\n`;
            
            for (let i = 0; i < data.sequences.length; i++) {
                const sequenceNum = i;
                const prefix = (i === 0) ? "║ GOD  " : (i === 1) ? "║ ANGEL" : `║ SEQ ${sequenceNum}`;
                tree += `${prefix} │ ${data.sequences[i]}\n`;
                if (i < data.sequences.length - 1) {
                    tree += "║      │\n";
                    tree += "║      ▼\n";
                }
            }
            tree += "╚═══════════════════════════════════════════════════════════════╝";
            return tree;
        }

        // Form submission handler
        document.getElementById('beyonderForm').addEventListener('submit', function(e) {
            e.preventDefault();
            
            const formData = new FormData(e.target);
            const name = formData.get('name') || document.getElementById('name').value;
            const epoch = document.getElementById('epoch').value;
            const church = document.getElementById('church').value;
            const pathway = document.getElementById('pathway').value;
            const sequence = parseInt(document.getElementById('sequence').value);
            
            if (!name || !epoch || !church || !pathway || sequence === null) {
                alert('Please fill in all fields to forge your destiny!');
                return;
            }
            
            generateBeyonder(name, epoch, church, pathway, sequence);
        });

        function generateBeyonder(name, epoch, church, pathway, sequence) {
            const resultsSection = document.getElementById('results');
            
            // Show loading
            resultsSection.innerHTML = '<div class="loading">Forging your mystical destiny</div>';
            resultsSection.classList.add('show');
            
            // Simulate processing time
            setTimeout(() => {
                const pathwayInfo = pathwayData[pathway];
                const epochInfo = epochData[epoch];
                const churchInfo = churchData[church];
                
                const sequenceName = pathwayInfo.sequences[sequence];
                const potionName = `${sequenceName} Potion`;
                const sequenceClass = getSequenceClass(sequence);
                const abilities = pathwayInfo.abilities[sequence];
                const pathwayTree = generatePathwayTree(pathway);
                
                resultsSection.innerHTML = `
                    <h2 class="section-title">Your Beyonder Profile</h2>
                    
                    <div class="result-item">
                        <span class="result-label">Name:</span>
                        <span class="result-value">${name}</span>
                    </div>
                    
                    <div class="result-item">
                        <span class="result-label">Epoch:</span>
                        <span class="result-value">${epochInfo.name}</span>
                    </div>
                    
                    <div class="result-item">
                        <span class="result-label">Church:</span>
                        <span class="result-value">${churchInfo.name}</span>
                    </div>
                    
                    <div class="result-item">
                        <span class="result-label">Pathway:</span>
                        <span class="result-value">${pathwayInfo.name}</span>
                    </div>
                    
                    <div class="result-item">
                        <span class="result-label">Sequence:</span>
                        <span class="result-value">Sequence ${sequence} - ${sequenceName}</span>
                    </div>
                    
                    <div class="result-item">
                        <span class="result-label">Potion:</span>
                        <span class="result-value">${potionName}</span>
                    </div>
                    
                    <div class="result-item">
                        <span class="result-label">Class:</span>
                        <span class="result-value">${sequenceClass}</span>
                    </div>
                    
                    <div class="abilities-list">
                        <h3 class="abilities-title">Beyonder Abilities</h3>
                        ${abilities.map(ability => `<div class="ability-item">${ability}</div>`).join('')}
                    </div>
                    
                    <div class="abilities-list">
                        <h3 class="abilities-title">Pathway Description</h3>
                        <div class="ability-item">${pathwayInfo.description}</div>
                    </div>
                    
                    <div class="abilities-list">
                        <h3 class="abilities-title">Epoch Influence</h3>
                        <div class="ability-item"><strong>Effect:</strong> ${epochInfo.influence}</div>
                        <div class="ability-item"><strong>Bonus:</strong> ${epochInfo.bonus}</div>
                    </div>
                    
                    <div class="abilities-list">
                        <h3 class="abilities-title">Church Benefits</h3>
                        <div class="ability-item"><strong>Authority:</strong> ${churchInfo.authority}</div>
                        <div class="ability-item"><strong>Benefits:</strong> ${churchInfo.benefits}</div>
                    </div>
                    
                    <div class="abilities-list">
                        <h3 class="abilities-title">Advancement Information</h3>
                        <div class="ability-item">
                            <strong>Current:</strong> Sequence ${sequence} - ${sequenceName}
                        </div>
                        ${sequence > 0 ? `
                            <div class="ability-item">
                                <strong>Next:</strong> Sequence ${sequence - 1} - ${pathwayInfo.sequences[sequence - 1]}
                            </div>
                        ` : `
                            <div class="ability-item">
                                <strong>Status:</strong> You have reached the pinnacle of this pathway! You are a True God!
                            </div>
                        `}
                    </div>
                    
                    <div class="pathway-tree">
                        ${pathwayTree}
                    </div>
                `;
            }, 1500);
        }

        // Initialize particles when page loads
        document.addEventListener('DOMContentLoaded', function() {
            createParticles();
        });

        // Add some interactive effects
        document.querySelectorAll('.input-field, .select-field').forEach(field => {
            field.addEventListener('focus', function() {
                this.parentElement.style.transform = 'translateY(-2px)';
                this.parentElement.style.transition = 'transform 0.3s ease';
            });
            
            field.addEventListener('blur', function() {
                this.parentElement.style.transform = 'translateY(0)';
            });
        });
    </script>
</body>
</html>
