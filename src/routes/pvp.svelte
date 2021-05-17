<script>
    import {
        CodeSnippet,
        Accordion,
        AccordionItem,
        Link,
        Tooltip,
    } from "carbon-components-svelte";
    import image from "images/2020-11-01_06.01.22.png";
</script>

<svelte:head>
    <title>pvpサーバー</title>
</svelte:head>

<h1>pvpサーバー</h1>

<p>
pvpサーバーの説明をする。
</p>

<Tooltip triggerText="ツールチップ？" align="start">
    <p>？マークを押すと説明が表示される</p>
</Tooltip>

<p>
    詳細は<Link href="https://azisabaofficial.playing.wiki/" target="_blank"
        >こちら</Link
    >みたいなこともできる
</p>

<!-- svelte-ignore a11y-missing-attribute -->
<img {image}>