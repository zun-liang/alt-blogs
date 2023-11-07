---
layout: post
title: Save Private API Keys in Environment Variables in Vite
---

<h4>Approach 1: Using the "VITE_Prefix" and "import.meta.env"</h4>
<p>Step 1: Create <code>.env</code> in the root directory<p>
<pre><code>
    VITE_REACT_APP_API_KEY = my_api_key
</code></pre>
<p>Step 2: Access environment variables using "import.meta.env"</p>
<p>Take <code>firebase.js</code> for example, </p>
<pre><code>
const firebaseConfig = {
apiKey: import.meta.env.VITE_REACT_APP_API_KEY,
};
</code></pre>
<p>Step 3: "vite.config.js" remains this same.</p>
<h4>Approach 2:  Using "loadEnv" for Configuration</h4>
<p>Step 1: Create <code>.env</code> in the root directory</p>
<pre><code>
    VITE_REACT_APP_API_KEY = my_api_key
</code></pre>
<p>Step 2: Access environment variables using "process.env"</p>
<p>Take <code>firebase.js</code> for example, </p>
<pre><code>
const firebaseConfig = {
apiKey: process.env.REACT_APP_API_KEY,
};
</code></pre>
<p>Step 3: Configure in "vite.config.js"</p>
<pre><code>
import react from &quot;@vitejs/plugin-react&quot;;
import { defineConfig, loadEnv } from &quot;vite&quot;;

<p>//vitejs.dev/config/
export default defineConfig(({ mode }) =&gt; {
    const env = loadEnv(mode, process.cwd(), &quot;&quot;);
    return {
        define: {
        &quot;process.env.REACT_APP_API_KEY&quot;: JSON.stringify(env.REACT_APP_API_KEY),
        },
        plugins: [react()],
    };
});
</code></pre></p>
