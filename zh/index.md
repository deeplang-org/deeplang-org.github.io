---
layout: base
lang: zh
title: DeepLang
description: DeepLang —— 面向 AIoT 与边缘 AI 的内存安全编程语言
---
{% assign t = site.data[page.lang] %}

<!-- Hero -->
<section class="hero">
    <div class="hero-inner">
        <img src="{{ '/assets/images/logo.jpg' | relative_url }}" alt="DeepLang Logo" class="hero-logo" width="80" height="80">
        <h1>{{ t.hero.title }}</h1>
        <h2>{{ t.hero.subtitle }}</h2>
        <p>{{ t.hero.description }}</p>
        <div class="hero-actions">
            <a href="https://github.com/deeplang-org/deeplang" class="btn btn-primary" target="_blank" rel="noopener">
                <svg width="20" height="20" viewBox="0 0 16 16" fill="currentColor"><path d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27s1.36.09 2 .27c1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.01 8.01 0 0 0 16 8c0-4.42-3.58-8-8-8z"/></svg>
                {{ t.hero.github_button }}
            </a>
            <a href="#features" class="btn btn-secondary">{{ t.hero.learn_more }}</a>
        </div>
    </div>
</section>

<!-- Features -->
<section class="section" id="features">
    <div class="section-inner">
        <div class="section-header">
            <h2>{{ t.features.title }}</h2>
            <p>{{ t.features.subtitle }}</p>
        </div>
        <div class="features-grid">
            {% for item in t.features.items %}
            <div class="feature-card">
                <span class="feature-icon">{{ item.icon }}</span>
                <h3>{{ item.title }}</h3>
                <p>{{ item.description }}</p>
            </div>
            {% endfor %}
        </div>
    </div>
</section>

<!-- Compiler & Type System -->
<section class="section" id="compiler">
    <div class="section-inner">
        <div class="section-header">
            <h2>{{ t.compiler.title }}</h2>
            <p>{{ t.compiler.subtitle }}</p>
        </div>
        <p class="compiler-intro">{{ t.compiler.description }}</p>

        <!-- Pipeline -->
        <div class="pipeline">
            {% for stage in t.compiler.pipeline %}
            <div class="pipeline-stage">
                <div class="pipeline-icon">{{ forloop.index }}</div>
                <div class="pipeline-name">{{ stage.name }}</div>
                <div class="pipeline-desc">{{ stage.desc }}</div>
            </div>
            {% if forloop.last == false %}
            <div class="pipeline-arrow">→</div>
            {% endif %}
            {% endfor %}
        </div>

        <!-- Type System Highlights -->
        <div class="type-highlights">
            <h3>{{ t.compiler.highlights.title }}</h3>
            <ul>
                {% for item in t.compiler.highlights.items %}
                <li>{{ item }}</li>
                {% endfor %}
            </ul>
        </div>

        <div class="compiler-cta">
            <a href="https://github.com/deeplang-org/deeplang-type-system" class="btn btn-primary" target="_blank" rel="noopener">
                <svg width="20" height="20" viewBox="0 0 16 16" fill="currentColor"><path d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27s1.36.09 2 .27c1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.01 8.01 0 0 0 16 8c0-4.42-3.58-8-8-8z"/></svg>
                {{ t.compiler.repo }}
            </a>
        </div>
    </div>
</section>

<!-- Code Example -->
<section class="section section-alt code-section" id="example">
    <div class="section-inner">
        <div class="section-header">
            <h2>{{ t.code_example.title }}</h2>
            <p>{{ t.code_example.subtitle }}</p>
        </div>
        <div class="code-block" id="codeBlock">
            <div class="code-block-header">
                <span class="code-dot red"></span><span class="code-dot yellow"></span><span class="code-dot green"></span>
                <span class="code-filename">geometry.dp</span>
                <button class="code-run-btn" id="runBtn" onclick="runCode()" title="编译并运行">
                    <svg width="14" height="14" viewBox="0 0 16 16" fill="currentColor"><path d="M4 2v12l10-6z"/></svg>
                    运行
                </button>
            </div>
<pre><code><span class="co">// 代数数据类型：几何形状</span>
<span class="kw">type</span> <span class="ty">Shape</span> [
    <span class="adt">Rectangle</span>(width: <span class="ty">F64</span>, height: <span class="ty">F64</span>),
    <span class="adt">Circle</span>(radius: <span class="ty">F64</span>),
    <span class="adt">Nothing</span>
]

<span class="co">// 接口：计算面积</span>
<span class="kw">interface</span> <span class="ty">Area</span> {
    <span class="kw">fun</span> <span class="fn">area</span>(<span class="kw">this</span>) -&gt; <span class="ty">F64</span>;
}

<span class="co">// 通过模式匹配为 Shape 实现 Area 接口</span>
<span class="kw">impl</span> <span class="ty">Area</span> <span class="kw">for</span> <span class="ty">Shape</span> {
    <span class="kw">fun</span> <span class="fn">area</span>() -&gt; <span class="ty">F64</span> {
        <span class="kw">match</span> (<span class="kw">this</span>) {
            <span class="adt">Rectangle</span>(w, h) =&gt; { <span class="kw">return</span> w * h; }
            <span class="adt">Circle</span>(r)       =&gt; { <span class="kw">return</span> <span class="num">3.14159</span> * r * r; }
            <span class="adt">Nothing</span>         =&gt; { <span class="kw">return</span> <span class="num">0.0</span>; }
        }
    }
}

<span class="kw">fun</span> <span class="fn">main</span>() -&gt; () {
    <span class="kw">let</span> rect: <span class="ty">Shape</span> = <span class="adt">Rectangle</span>(<span class="num">3.0</span>, <span class="num">4.0</span>);
    <span class="kw">let</span> circ: <span class="ty">Shape</span> = <span class="adt">Circle</span>(<span class="num">2.5</span>);
    <span class="fn">print</span>(rect.<span class="fn">area</span>().<span class="fn">toString</span>());  <span class="co">// 12.0</span>
    <span class="fn">print</span>(circ.<span class="fn">area</span>().<span class="fn">toString</span>());  <span class="co">// 19.6349</span>
}</code></pre>
            <!-- Compilation & Output -->
            <div class="code-compile" id="codeCompile" style="display:none">
                <div class="compile-label">编译中...</div>
                <div class="compile-stages" id="compileStages">
                    <span class="compile-stage">词法分析</span>
                    <span class="compile-arr">→</span>
                    <span class="compile-stage">语法解析</span>
                    <span class="compile-arr">→</span>
                    <span class="compile-stage">语义分析</span>
                    <span class="compile-arr">→</span>
                    <span class="compile-stage">ANF</span>
                    <span class="compile-arr">→</span>
                    <span class="compile-stage">WAT</span>
                </div>
                <div class="compile-progress"><div class="compile-bar" id="compileBar"></div></div>
            </div>
            <div class="code-output" id="codeOutput" style="display:none">
                <div class="output-label">▶ 终端输出</div>
<pre><code>12.0
19.6349375</code></pre>
            </div>
        </div>
    </div>
</section>

<!-- DeepVM -->
<section class="section" id="deepvm">
    <div class="section-inner">
        <div class="section-header">
            <h2>{{ t.deepvm.title }}</h2>
            <p>{{ t.deepvm.subtitle }}</p>
        </div>
        <div class="vm-content">
            <div>
                <p class="vm-description">{{ t.deepvm.description }}</p>
                <div class="vm-specs">
                    {% for spec in t.deepvm.specs %}
                    <div class="vm-spec">
                        <span class="vm-spec-value">{{ spec.value }}</span>
                        <span class="vm-spec-label">{{ spec.label }}</span>
                    </div>
                    {% endfor %}
                </div>
            </div>
            <div class="vm-targets">
                <h3>{{ t.deepvm.targets.title }}</h3>
                <ul>
                    {% for chip in t.deepvm.targets.items %}
                    <li>{{ chip }}</li>
                    {% endfor %}
                </ul>
            </div>
        </div>
    </div>
</section>

<!-- Team -->
<section class="section section-alt" id="team">
    <div class="section-inner">
        <div class="section-header">
            <h2>{{ t.team.title }}</h2>
            <p>{{ t.team.subtitle }}</p>
        </div>
        <div class="team-list">
            {% for uni in t.team.universities %}
            <div class="team-card">
                <div class="uni-name">{{ uni.name }}</div>
                <div class="uni-role">核心贡献者</div>
            </div>
            {% endfor %}
        </div>
        <div class="team-cta">
            <p>{{ t.team.join }}</p>
            <div class="team-links">
                <a href="https://github.com/deeplang-org/deeplang/wiki/CCB-Memnbers" class="btn btn-primary" target="_blank" rel="noopener">{{ t.team.ccb }}</a>
                <a href="mailto:swubear@163.com" class="btn btn-secondary">{{ t.team.contact }}</a>
            </div>
        </div>
    </div>
</section>
