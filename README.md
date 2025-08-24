<br/>
<h1 align="center">Vilya</h1>
<br/>

<p align="center">
Vilya is an <strong>ultra-fast scalable Static Site Generator (SSG)</strong> designed to transform <strong>structured JSON into static websites</strong> using <strong>React</strong>.
  
  <br/>
  Using a flexible plugin pipeline. Its philosophy is simple: <strong>lightweight, fast, and reliable</strong>  even for projects with millions of pages with a strong focus on <strong>partial-hydration</strong> and <strong>incremental builds.</strong>
</p>


---

## 🔹 Philosophy

- **Maximum speed**: streaming processing, worker-based parallelization, and incremental builds.  
- **Minimal RAM usage**: each page is processed individually and released immediately.  
- **Flexible**: plugin architecture inspired by Metalsmith using `.use()`.  
- **React-first**: central layout and reusable components for static rendering and optional selective hydration.

---

## 🔹 Key features

- Declarative pipeline:
  
```javascript
  const vilya = new Vilya({
    pageConcurrency: 10,
    workerCount: 2
  }); 

  vilya
    .source("./store")
    .use(parseJson())
    .use(applyLayout())
    .use(minifyHtml())
    .use(writeOut("./dist"))
    .postBuild(generateSitemap)
    .build();
```
