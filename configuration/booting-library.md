<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Booting the Library | LMF Developer Docs</title>
    <link rel="stylesheet" href="../style.css">
    <style> /* Same as above */ </style>
</head>
<body>
    <header>
        <h1><a href="../">LMF</a></h1>
        <nav><!-- Same nav --></nav>
    </header>
    <main>
        <h1>Booting the Library</h1>
        <hr>

        <h2>Loading the LMF Library</h2>
        <p>To get started, load the library using HttpService (enable HTTP requests in Studio).</p>
        <pre><code class="lua">local LMF = loadstring(game:HttpGet('https://raw.githubusercontent.com/yourusername/LMF/main/init.lua'))()</code></pre>

        <div class="tip">
            <strong>Tip:</strong> Make sure your script runs after the player loads. Use in a LocalScript for client-side.
        </div>

        <h2>Enabling Configuration Saving</h2>
        <p>LMF supports auto-saving configs. Follow these steps:</p>
        <ol>
            <li>Enable <code>ConfigurationSaving</code> in <code>CreateWindow()</code>.</li>
            <li>Choose a unique <code>FileName</code> in <code>CreateWindow()</code>.</li>
            <li>Use unique flag identifiers for all elements (e.g., toggles, sliders).</li>
            <li>Call <code>LMF:LoadConfiguration()</code> at the end of your script.</li>
        </ol>
        <pre><code class="lua">local Window = LMF:CreateWindow({
    Name = "My App",
    ConfigurationSaving = {
        Enabled = true,
        FolderName = "LMFConfig",
        FileName = "MyConfig.json"
    }
})

-- Your UI elements here...

LMF:LoadConfiguration()</code></pre>

        <hr>
        <p>Next: <a href="../api">API Reference</a></p>
    </main>
</body>
</html>
