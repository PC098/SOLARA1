<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Solara: Interactive Data Dashboards in Python</title>
    <style>
        body { font-family: Arial, sans-serif; line-height: 1.6; margin: 40px; padding: 20px; max-width: 900px; margin: auto; }
        h1, h2, h3 { color: #2c3e50; }
        pre { background: #f4f4f4; padding: 10px; border-radius: 5px; overflow-x: auto; }
        code { font-family: monospace; color: #d63384; }
        .toc { background: #ecf0f1; padding: 10px; border-radius: 5px; }
        .toc a { display: block; text-decoration: none; color: #2980b9; padding: 5px; }
        .toc a:hover { text-decoration: underline; }
    </style>
</head>
<body>
    <h1>Solara: A Framework for Creating Interactive Data Dashboards in Python</h1>
    
    <div class="toc">
        <h3>Table of Contents</h3>
        <a href="#intro">Introduction</a>
        <a href="#install">Installation & Setup</a>
        <a href="#features">Key Features & Explanation</a>
        <a href="#code">Code Examples</a>
        <a href="#usecases">Use Cases</a>
        <a href="#conclusion">Conclusion</a>
        <a href="#references">References & Further Reading</a>
    </div>
    
    <h2 id="intro">Introduction</h2>
    <p>Solara is a powerful framework that allows developers to build interactive data dashboards using Python. It combines the simplicity of Python with the flexibility of React-like components.</p>
    
    <h2 id="install">Installation & Setup</h2>
    <p>To install Solara, run:</p>
    <pre><code>pip install solara</code></pre>
    <p>After installation, start a development server with:</p>
    <pre><code>solara run</code></pre>
    
    <h2 id="features">Key Features & Explanation</h2>
    <ul>
        <li><b>Reactive Components:</b> Components update automatically when state changes.</li>
        <li><b>Integration with Jupyter & FastAPI:</b> Suitable for data science and web apps.</li>
        <li><b>Built-in Widgets:</b> Interactive elements like sliders, dropdowns, and buttons.</li>
        <li><b>Markdown & Plots Support:</b> Works with Matplotlib, Plotly, and Altair.</li>
    </ul>
    
    <h2 id="code">Code Examples</h2>
    <h3>Basic Example</h3>
    <pre><code>import solara

@solara.component
def Page():
    name = solara.use_state("World")
    solara.InputText("Enter your name:", value=name)
    solara.Button("Greet", on_click=lambda: print(f"Hello, {name.value}!"))
    solara.Text(f"Hello, {name.value}!")

solara.run(Page)</code></pre>
    
    <h3>Interactive Plot Example</h3>
    <pre><code>import solara
import matplotlib.pyplot as plt
import numpy as np

@solara.component
def Page():
    a = solara.use_state(1.0)
    b = solara.use_state(0.0)
    x = np.linspace(-10, 10, 100)
    y = a.value * x + b.value

    fig, ax = plt.subplots()
    ax.plot(x, y)
    solara.FigureMatplotlib(fig)

    solara.SliderFloat("Slope (a)", value=a, min=-5, max=5)
    solara.SliderFloat("Intercept (b)", value=b, min=-5, max=5)

solara.run(Page)</code></pre>
    
    <h2 id="usecases">Use Cases</h2>
    <ul>
        <li><b>Data Science Dashboards:</b> Visualize and interact with data.</li>
        <li><b>Real-time Data Monitoring:</b> Build business analytics dashboards.</li>
        <li><b>Interactive Educational Tools:</b> Create learning applications.</li>
        <li><b>Prototyping Web Apps:</b> Quickly prototype applications with Python.</li>
    </ul>
    
    <h2 id="conclusion">Conclusion</h2>
    <p>Solara is an excellent framework for building interactive dashboards. It simplifies UI development while offering powerful features for data visualization and interactivity.</p>
    
    <h2 id="references">References & Further Reading</h2>
    <ul>
        <li><a href="#">Solara Documentation</a></li>
        <li><a href="#">GitHub Repository</a></li>
        <li><a href="#">FastAPI</a></li>
        <li><a href="#">Matplotlib</a></li>
    </ul>
</body>
</html>

