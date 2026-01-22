<!DOCTYPE html>
<html>
<head>
    <title>Lesson Builder</title>
    <script src="https://www.gstatic.com/firebasejs/9.17.1/firebase-app-compat.js"></script>
    <script src="https://www.gstatic.com/firebasejs/9.17.1/firebase-database-compat.js"></script>
    <style>
        body { background: #1a1a2e; color: white; font-family: sans-serif; padding: 20px; text-align: center; }
        .container { max-width: 1200px; margin: 0 auto; }
        
        /* Top Bar */
        .top-bar { background: #222; padding: 20px; border-radius: 10px; border: 1px solid #444; display: flex; justify-content: space-between; align-items: center; margin-bottom: 20px; }
        input[type="text"] { padding: 10px; border-radius: 5px; border: 1px solid #555; background: #000; color: white; width: 300px; }
        button { padding: 10px 20px; font-weight: bold; border-radius: 5px; border: none; cursor: pointer; }
        .btn-green { background: #28a745; color: white; }
        
        /* Grid */
        .grid { display: grid; gap: 10px; grid-template-columns: repeat(6, 1fr); }
        .col-header input { width: 90%; background: #16213e; color: #00d2ff; font-weight: bold; text-align: center; border: 1px solid #00d2ff; padding: 10px; }
        .cell { background: #111; border: 1px dashed #444; padding: 15px; border-radius: 5px; cursor: pointer; height: 60px; display: flex; align-items: center; justify-content: center; }
        .cell:hover { border-color: #ffd700; background: #222; }
        
        /* Popup Editor */
        #editor-overlay { display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: rgba(0,0,0,0.9); z-index: 1000; justify-content: center; align-items: center; }
        .editor-box { background: #222; padding: 30px; border: 2px solid #00d2ff; border-radius: 10px; width: 500px; text-align: left; }
        textarea { width: 100%; height: 80px; background: #000; color: white; border: 1px solid #555; margin-bottom: 15px; padding: 10px; box-sizing: border-box; }
        label { display: block; margin-bottom: 5px; color: #aaa; }
    </style>
</head>
<body>

    <div class="container">
        <div class="top-bar">
            <h2>🛠️ Lesson Builder</h2>
            <input type="text" id="lesson-name" placeholder="Enter Lesson Name (e.g., Biology 101)">
            <button class="btn-green" onclick="saveLesson()">💾 SAVE TO DATABASE</button>
        </div>

        <div id="grid-container" class="grid"></div>
    </div>

    <div id="editor-overlay">
        <div class="editor-box">
            <h3>Edit Tile</h3>
            <label>Question:</label>
            <textarea id="edit-q"></textarea>
            <label>Answer:</label>
            <textarea id="edit-a"></textarea>
            <div style="text-align: right;">
                <button onclick="closeEditor()" style="background: #e94560; color: white; margin-right: 10px;">Cancel</button>
                <button onclick="saveTile()" style="background: #28a745; color: white;">Save Tile</button>
            </div>
        </div>
    </div>

    <script>
        const config = { apiKey: "AIzaSyBYYe4I-spWUJ6ORpbue_XKT8pqowmQNqo", authDomain: "trivia-game-3fe59.firebaseapp.com", databaseURL: "https://trivia-game-3fe59-default-rtdb.firebaseio.com", projectId: "trivia-game-3fe59", appId: "1:851139559118:web:df59f13dfd9234c1e89a9f" };
        firebase.initializeApp(config);
        const db = firebase.database();

        let builderData = { categories: [] };
        let activeCoords = null;

        // Initialize empty board
        function init() {
            for(let c=0; c<6; c++) {
                let items = [];
                for(let r=0; r<5; r++) items.push({ q: "Question", a: "Answer" });
                builderData.categories.push({ name: "Category " + (c+1), items: items });
            }
            render();
        }

        function render() {
            const grid = document.getElementById('grid-container');
            grid.innerHTML = "";
            
            // Headers
            builderData.categories.forEach((cat, cIdx) => {
                let d = document.createElement('div');
                d.className = "col-header";
                let inp = document.createElement('input');
                inp.value = cat.name;
                inp.onchange = (e) => { builderData.categories[cIdx].name = e.target.value; };
                d.appendChild(inp);
                grid.appendChild(d);
            });

            // Cells
            for(let r=0; r<5; r++) {
                builderData.categories.forEach((cat, cIdx) => {
                    let c = document.createElement('div');
                    c.className = "cell";
                    c.innerText = "$" + (200*(r+1));
                    c.onclick = () => openEditor(cIdx, r);
                    grid.appendChild(c);
                });
            }
        }

        function openEditor(c, r) {
            activeCoords = { c, r };
            const item = builderData.categories[c].items[r];
            document.getElementById('edit-q').value = item.q;
            document.getElementById('edit-a').value = item.a;
            document.getElementById('editor-overlay').style.display = 'flex';
        }

        function saveTile() {
            const q = document.getElementById('edit-q').value;
            const a = document.getElementById('edit-a').value;
            builderData.categories[activeCoords.c].items[activeCoords.r] = { q, a };
            closeEditor();
        }

        function closeEditor() {
            document.getElementById('editor-overlay').style.display = 'none';
        }

        function saveLesson() {
            const name = document.getElementById('lesson-name').value.trim();
            if(!name) return alert("Please enter a lesson name first!");
            
            db.ref('library/' + name).set(builderData, (error) => {
                if(error) {
                    alert("Error saving: " + error.message);
                } else {
                    alert("SUCCESS! Lesson '" + name + "' saved.\nYou can now close this tab and select it in the Teacher Board.");
                }
            });
        }

        init();
    </script>
</body>
</html>
