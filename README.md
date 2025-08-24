# Vilya

> *"The Ring of Air that Guides Creation"* – Inspired by Tolkien

Vilya is an **ultra-fast, scalable Static Site Generator (SSG)** designed to transform **structured JSON into static websites** using **React** with a flexible plugin pipeline.  
Its philosophy is simple: **lightweight, fast, and reliable**, even for projects with millions of pages with a strong focus on partial-hydration and incremental builds.

---

## 🔹 Philosophy

- **Maximum speed**: streaming processing, worker-based parallelization, and incremental builds.  
- **Minimal RAM usage**: each page is processed individually and released immediately.  
- **Flexible**: plugin architecture inspired by Metalsmith/Express using `.use()`.  
- **React-first**: central layout and reusable components for static rendering and optional selective hydration.

---

## 🔹 Key Features (Planned)

- Declarative pipeline:
  ```ts
  const ssg = new Vilya({ batchSize: 10 });

  ssg
    .source("./pages-json")
    .use(parseJson())
    .use(applyLayout())
    .use(minifyHtml())
    .use(writeOut("./dist"))
    .postBuild(generateSitemap)
    .build();
