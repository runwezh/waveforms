<script>
    import { Router, Route } from "svelte-routing";
    import { COLORS } from "./constants";
    import IntroRoute from "./components/IntroRoute.svelte";
    import Footer from "./components/Footer.svelte";
</script>
  
<Router>
    <div>
      <Route path="/" component={IntroRoute} />
      <Footer />
    </div>
</Router>
  
<style>
    /* 全局样式 */
    :global(body) {
      background: var(--color-gray-50);
      color: var(--color-gray-800);
    }
  
    :global(:root) {
      --color-gray-50: #f9fafb;
      --color-gray-800: #1f2937;
      /* 添加其他需要的颜色变量 */
    }
</style>