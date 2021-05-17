<script>
    import {
        CodeSnippet,
        Accordion,
        AccordionItem,
        Link,
        Tooltip,
    } from "carbon-components-svelte";

    function copy(text) {
        navigator.clipboard.writeText(text);
    }

    const proxyProvider = {
        aws: {
            name: "Amazon Web Services",
            domain: "aws.amazon.com",
        },
        vultr: {
            name: "Vultr",
            domain: "www.vultr.com",
        },
    };

    const proxyServers = [
        {
            name: "DDPS1",
            ip: "54.250.163.61:35575",
            uptimeRobotApiKey: "m784491883-ee0edb2f453aee35dc6c2d3b",
            provider: proxyProvider.aws,
        },
        {
            name: "DDPS2",
            ip: "13.231.99.109:35575",
            uptimeRobotApiKey: "m784491888-d82caba675aa6d3b96f2293b",
            provider: proxyProvider.aws,
        },
        {
            name: "DDPS3",
            ip: "54.199.141.66:35575",
            uptimeRobotApiKey: "m784491889-3aa7bf6dca41a5f40153feed",
            provider: proxyProvider.aws,
        },
        {
            name: "DDPS4",
            ip: "167.179.81.253:35575",
            uptimeRobotApiKey: "m784946618-df83183700506722cd43b630",
            provider: proxyProvider.vultr,
        },
        {
            name: "DDPS5",
            ip: "202.182.123.235:35575",
            uptimeRobotApiKey: "m784946613-b1de29e51d6d00fdba2a116d",
            provider: proxyProvider.vultr,
        },
        {
            name: "DDPS6",
            ip: "45.77.10.15:35575",
            uptimeRobotApiKey: "m784946609-8f545489caf7fcdf66ce38b0",
            provider: proxyProvider.vultr,
        },
    ];
</script>

<svelte:head>
    <title>各サーバー紹介</title>
</svelte:head>

<h1>各サーバー紹介</h1>

<p>準備中...</p>

