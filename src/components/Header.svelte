<script>
    import {
        Header,
        HeaderUtilities,
        HeaderActionLink,
        HeaderAction,
        HeaderPanelLinks,
        HeaderPanelDivider,
        HeaderPanelLink,
        SideNav,
        SideNavItems,
        SideNavMenu,
        SideNavLink,
        SkipToContent,
    } from "carbon-components-svelte";

    import LightFilled24 from "carbon-icons-svelte/lib/LightFilled24";
    import ChatBot24 from "carbon-icons-svelte/lib/ChatBot24";
    import LogoYoutube24 from "carbon-icons-svelte/lib/LogoYoutube24";
    import LogoTwitter24 from "carbon-icons-svelte/lib/LogoTwitter24";
    import LogoGithub24 from "carbon-icons-svelte/lib/LogoGithub24";

    import ChatBot32 from "carbon-icons-svelte/lib/ChatBot32";
    import LogoYoutube32 from "carbon-icons-svelte/lib/LogoYoutube32";
    import LogoTwitter32 from "carbon-icons-svelte/lib/LogoTwitter32";
    import LogoGithub32 from "carbon-icons-svelte/lib/LogoGithub32";

    import FavoriteFilled32 from "carbon-icons-svelte/lib/FavoriteFilled32";
    import Fish32 from "carbon-icons-svelte/lib/Fish32";
    import Book32 from "carbon-icons-svelte/lib/Book32";
    import PlayOutline32 from "carbon-icons-svelte/lib/PlayOutline32";
    import Locked32 from "carbon-icons-svelte/lib/Locked32";

    export let segment;

    const socials = [
        {
            name: "Discord",
            iconMini: ChatBot24,
            icon: ChatBot32,
            url: "https://discord.gg/azisaba",
        },
        {
            name: "Twitter",
            iconMini: LogoTwitter24,
            icon: LogoTwitter32,
            url: "https://twitter.com/AzisabaNetwork",
        },
        {
            name: "YouTube",
            iconMini: LogoYoutube24,
            icon: LogoYoutube32,
            url: "https://www.youtube.com/channel/UCHkH9_MKql1MFi0MZ_tqQbg",
        },
        {
            name: "GitHub",
            iconMini: LogoGithub24,
            icon: LogoGithub32,
            url: "https://github.com/azisaba",
        },
    ];

    const menu = [
        "Wiki",
        {
            name: "公式Wiki",
            url: "https://azisabaofficial.playing.wiki",
        },
        {
            name: "非公式Wiki",
            url: "https://aziserver.playing.wiki",
        },
        "投票する",
        {
            name: "Japan Minecraft Servers",
            url: "https://minecraft.jp/servers/azisaba.net",
        },
        {
            name: "monocraft",
            url: "https://monocraft.net/servers/xWBVrf1nqB2P0LxlMm2v",
        },
        {
            name: "NameMC",
            url: "https://ja.namemc.com/server/azisaba.net",
        },
    ];

    let innerWidth;
    $: isMobile = innerWidth < 1056;

    let isSideNavOpen = false;
</script>

<svelte:window bind:innerWidth />

<Header
    company="アジ鯖"
    platformName="公式ホームページ"
    href="/"
    bind:isSideNavOpen
>
    <div slot="skip-to-content">
        <SkipToContent />
    </div>

    <HeaderUtilities>
        {#if !isMobile}
            <HeaderActionLink
                    title="Toggle dark <-> light mode"
                    icon={{ render: LightFilled24 }}
                    onclick="toggleDarkMode()"
            />
            {#each socials as social}
                <HeaderActionLink
                    title={social.name}
                    icon={{ render: social.iconMini }}
                    href={social.url}
                    target="_blank"
                />
            {/each}
        {/if}

        <HeaderAction>
            <HeaderPanelLinks>
                {#each menu as item}
                    {#if typeof item == "string"}
                        <HeaderPanelDivider>{item}</HeaderPanelDivider>
                    {:else}
                        <HeaderPanelLink href={item.url} target="_blank"
                            >{item.name}</HeaderPanelLink
                        >
                    {/if}
                {/each}
            </HeaderPanelLinks>
        </HeaderAction>
    </HeaderUtilities>
</Header>

<SideNav bind:isOpen={isSideNavOpen}>
    <SideNavItems>
        <SideNavMenu text="はじめに" expanded={true}>
            <SideNavLink
                icon={{ render: FavoriteFilled32 }}
                text="ようこそ"
                href="/"
                isSelected={segment === undefined}
            />
            <SideNavLink
                icon={{ render: Fish32 }}
                text="アジ鯖とは？"
                href="/intro"
                isSelected={segment === "intro"}
            />
            <SideNavLink
                icon={{ render: Book32 }}
                text="ルール"
                href="/terms"
                isSelected={segment === "terms"}
            />
            <SideNavLink
                icon={{ render: PlayOutline32 }}
                text="今すぐ参加"
                href="/join"
                isSelected={segment === "join"}
            />
        </SideNavMenu>
        <SideNavMenu text="もっと詳しく" expanded={true}>
            <SideNavLink icon={{ render: Locked32 }} text="各サーバー紹介" />
            <SideNavLink icon={{ render: Locked32 }} text="アルバム" />
            <SideNavLink icon={{ render: Locked32 }} text="運営一覧" />
            <SideNavLink icon={{ render: Locked32 }} text="スポンサー" />
        </SideNavMenu>
        <SideNavMenu text="その他">
            <SideNavLink
                text="接続チェック"
                href="https://mcsrvstat.us/server/azisaba.net"
                target="_blank"
            />
            <SideNavLink
                text="リソースパックのダウンロード"
                href="https://packs.azisaba.net"
                target="_blank"
            />
        </SideNavMenu>
        <SideNavMenu text="共有する" expanded={true}>
            {#each socials as social}
                <SideNavLink
                    icon={{ render: social.icon }}
                    text={social.name}
                    href={social.url}
                    target="_blank"
                />
            {/each}
        </SideNavMenu>
    </SideNavItems>
</SideNav>
