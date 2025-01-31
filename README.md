# Ary
<!DOCTYPE html>
<html>
<head>
    <title>Arduino Web IDE</title>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/ace/1.4.12/ace.js"></script>
    <style>
        body { font-family: Arial, sans-serif; text-align: center; }
        #editor { width: 90%; height: 300px; margin: auto; border: 1px solid #ddd; }
        button { margin-top: 10px; padding: 10px; font-size: 16px; }
    </style>
</head>
<body>
    <h2>Arduino Web Editor</h2>
    <div id="editor">void setup() {\n  pinMode(13, OUTPUT);\n}\n\nvoid loop() {\n  digitalWrite(13, HIGH);\n  delay(1000);\n  digitalWrite(13, LOW);\n  delay(1000);\n}</div>
    <br>
    <button onclick="compileCode()">Compile</button>
    <button onclick="saveCode()">Save</button>

    <script>
        var editor = ace.edit("editor");
        editor.setTheme("ace/theme/monokai");
        editor.session.setMode("ace/mode/c_cpp");

        function compileCode() {
            alert("Compilation Started (Backend Not Connected)!");
        }

        function saveCode() {
            var text = editor.getValue();
            var blob = new Blob([text], { type: "text/plain" });
            var a = document.createElement("a");
            a.href = URL.createObjectURL(blob);
            a.download = "sketch.ino";
            a.click();
        }
    </script>
</body>
</html>
