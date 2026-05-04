<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>🌿 Botanical Journey 🌿</title>
    <style>
        :root {
            --primary-green: #2e7d32;
            --light-green: #e8f5e9;
            --accent-green: #81c784;
            --text-dark: #1b5e20;
            --bg-color: #f1f8e9;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: var(--bg-color);
            color: var(--text-dark);
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }

        #simulator-container {
            background-color: white;
            border: 2px solid var(--accent-green);
            border-radius: 15px;
            box-shadow: 0 10px 20px rgba(0,0,0,0.1);
            width: 90%;
            max-width: 600px;
            padding: 30px;
            text-align: center;
            position: relative;
        }

        h1 {
            color: var(--primary-green);
            margin-top: 0;
            border-bottom: 2px dashed var(--light-green);
            padding-bottom: 10px;
        }

        #story-text {
            font-size: 1.1em;
            line-height: 1.5;
            margin-bottom: 25px;
            min-height: 150px;
            text-align: left;
        }

        .ascii-art {
            font-family: 'Courier New', Courier, monospace;
            white-space: pre;
            text-align: center;
            color: var(--primary-green);
            margin: 15px 0;
            font-size: 1.2em;
            line-height: 1.1;
        }

        .concept-check {
            background-color: var(--light-green);
            border-left: 4px solid var(--primary-green);
            padding: 12px;
            margin-top: 15px;
            border-radius: 0 8px 8px 0;
            font-size: 0.95em;
        }

        .button-container {
            display: flex;
            flex-direction: column;
            gap: 12px;
        }

        button {
            background-color: var(--primary-green);
            color: white;
            border: none;
            padding: 12px 18px;
            font-size: 1em;
            border-radius: 8px;
            cursor: pointer;
            transition: 0.2s;
            font-weight: bold;
        }

        button:hover {
            background-color: #1b5e20;
            transform: translateY(-2px);
        }

        .fade-in {
            animation: fadeIn 0.4s ease-in;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(5px); }
            to { opacity: 1; transform: translateY(0); }
        }
    </style>
</head>
<body>

    <div id="simulator-container" class="fade-in">
        <h1 id="scene-title">🌿 Botanical Journey</h1>
        <div id="story-text">Loading...</div>
        <div class="button-container" id="choices-container"></div>
    </div>

    <script>
        const storyBranches = {
            start: {
                title: "🌿 Welcome to Botanical Journey",
                text: "<div class='ascii-art'>   .o00o.\n  o000000o\n  00000000\n   '0000'\n     ||\n    /||\\ </div>🪴 <strong>Your plant is mature!</strong> It's time to reproduce and secure the next generation. Ready to play Mother Nature? 🌍",
                choices: [{ text: "🚀 Begin Simulation", target: "reproduction_choice" }]
            },
            reproduction_choice: {
                title: "🧬 Phase 1: Reproduction",
                text: "How will your plant generate offspring? 🤔",
                choices: [
                    { text: "🌱 Path A: Asexual (Vegetative)", target: "asexual_path" },
                    { text: "🌸 Path B: Sexual (Flowering)", target: "sexual_path" }
                ]
            },
            asexual_path: {
                title: "🌱 Path A: Asexual Reproduction",
                text: "<div class='ascii-art'> 🌱    🌱    🌱\n  |------|------|\n / \\    / \\    / \\ </div>🏃‍♂️ Your plant sends out vegetative runners using <strong>mitotic cell division</strong>. <br><br><div class='concept-check'><strong>🧬 Concept Check:</strong> No gamete fusion = Offspring are <strong>genetically identical clones</strong> 🐑. <br><br>✅ <strong>Pro:</strong> Super fast!<br>❌ <strong>Con:</strong> Zero genetic diversity. One disease 🦠 could wipe out the whole field!</div>",
                choices: [{ text: "⏪ Restart to explore Path B", target: "start" }]
            },
            sexual_path: {
                title: "🌸 Path B: Sexual Reproduction",
                text: "<div class='ascii-art'>      _ _\n    _{ ' }_\n   { `.!.` }\n   ',_/Y\\_,'\n     {_,_}\n       |\n     \\|/ </div>🌺 Your plant grows vibrant flowers! This path fuses <strong>male ♂️ and female ♀️ gametes</strong> created via <strong>meiosis</strong> ➗.",
                choices: [{ text: "🐝 Proceed to Pollination", target: "pollination_phase" }]
            },
            pollination_phase: {
                title: "🐝 Phase 2: Pollination",
                text: "Pollen (male) must reach the stigma (female). Choose your strategy! 🎯",
                choices: [
                    { text: "🔄 Self-Pollination (Same plant)", target: "self_pollination" },
                    { text: "🔀 Cross-Pollination (Different plant)", target: "cross_pollination" }
                ]
            },
            self_pollination: {
                title: "🔄 Self-Pollination",
                text: "Pollen moves within the <em>same</em> flower 🌸➔🌸.<br><br><div class='concept-check'><strong>📉 Genetic Variation:</strong> <strong>LESS</strong> variation. <br>Reliable, but limits your plant's ability to adapt to new environmental threats 🏜️.</div>",
                choices: [{ text: "✨ Continue to Fertilization", target: "fertilization_phase" }]
            },
            cross_pollination: {
                title: "🔀 Cross-Pollination",
                text: "Pollen travels to a <em>different</em> plant 🌸➔🌼.<br><br><div class='concept-check'><strong>📈 Genetic Variation:</strong> <strong>GREATER</strong> variation. <br>Mixing DNA gives offspring a higher chance to survive changing environments 🌍!</div>",
                choices: [{ text: "✨ Continue to Fertilization", target: "fertilization_phase" }]
            },
            fertilization_phase: {
                title: "✨ Phase 3: Fertilization",
                text: "<div class='ascii-art'>   \\|/ 🐝\n    |\n   (O) </div>🔬 A pollen tube grows down the <strong>style</strong>. Male & female gametes fuse! 💥<br><br><div class='concept-check'><strong>🪄 Metamorphosis Check:</strong><br>🥚 <strong>Ovule</strong> ➔ Transforms into the 🌰 <strong>Seed</strong><br>🛡️ <strong>Ovary</strong> ➔ Ripens into the 🍎 <strong>Fruit</strong></div>",
                choices: [{ text: "🎒 Proceed to Seed Dispersal", target: "dispersal_phase" }]
            },
            dispersal_phase: {
                title: "🎒 Phase 4: Seed Dispersal",
                text: "Don't drop your seeds right here! Pick a travel method 🧳:",
                choices: [
                    { text: "💨 Wind (Parachutes/Wings)", target: "final_concept" },
                    { text: "💧 Water (Buoyant husks)", target: "final_concept" },
                    { text: "🐾 Animal (Tasty fruits/Burs)", target: "final_concept" }
                ]
            },
            final_concept: {
                title: "🏆 Simulation Complete!",
                text: "<div class='ascii-art'>  * .  * .  *\n .  🌍 SUCCESS! . \n  * .  * .  *</div>Your seeds traveled safely! The next generation is secure. 🌱<br><br><div class='concept-check'><strong>💡 Why is dispersal vital?</strong><br>1️⃣ <strong>Stop overcrowding:</strong> Avoid fighting the parent plant for light & water 🥊.<br>2️⃣ <strong>Colonize:</strong> Spread to new, thriving habitats 🗺️!</div>",
                choices: [{ text: "🔄 Play Again", target: "start" }]
            }
        };

        const titleElement = document.getElementById('scene-title');
        const textElement = document.getElementById('story-text');
        const choicesContainer = document.getElementById('choices-container');
        const simulatorContainer = document.getElementById('simulator-container');

        function renderScene(sceneKey) {
            const scene = storyBranches[sceneKey];
            
            simulatorContainer.classList.remove('fade-in');
            void simulatorContainer.offsetWidth; 
            simulatorContainer.classList.add('fade-in');

            titleElement.innerHTML = scene.title;
            textElement.innerHTML = scene.text;
            choicesContainer.innerHTML = '';

            scene.choices.forEach(choice => {
                const btn = document.createElement('button');
                btn.innerHTML = choice.text;
                btn.onclick = () => renderScene(choice.target);
                choicesContainer.appendChild(btn);
            });
        }

        renderScene('start');
    </script>
</body>
</html>
