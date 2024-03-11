<script>

    import Avatar from '$lib/components/ui/avatar/avatar.svelte';
    import AvatarFallback from '$lib/components/ui/avatar/avatar-fallback.svelte';
    import { AvatarImage } from '$lib/components/ui/avatar';
    let navLinks = [
        { text: 'Home', iconLink: 'images/nav/home.svg' },
        { text: 'Explore', iconLink: 'images/nav/explore.svg' },
        { text: 'Learn', iconLink: 'images/nav/learn.svg' }
    ];
</script>

<style>
    .navbar {
        display: flex;
        align-items: center;
        justify-content: space-between;
        padding: 8px;
        background-color: white; 
        color: #4D4D4D;
        border-bottom: 1px dotted #9ca2ab;
        height: 48px;
        margin-left: 5%;
        margin-right: 5%;
    }

    .nav-links {
        display: flex;
        align-items: center;
        gap: 48px;
        font-size: 14px;
    }

    .nav-links a {
        color: #4D4D4D; 
        text-decoration: none;
    }

    .nav-links a:hover {
        text-decoration: underline;
    }

    .nav-links .raised-button {
        box-shadow: 0px 4px 0px 0px #4D4D4D;
        background-color: white;
        color: #4D4D4D;
        border: 0.5px solid #4D4D4D;
        margin-top: 4px;
    }

    .logo {
        display: flex;
        align-items: center;
        gap: 10px;
    }

    .logo img {
        width: 27px;
        height: 27px;
        border-radius: 20%;
    }

    .logo span {
        font-size: 20px;
        font-weight: 700;
        color: #4D4D4D;
        padding-bottom: 5px;
    }
    .navigation {
        display: flex;
        align-items: center;
    }

    .nav-link {
        display:flex;
        flex-direction: row;
        align-items: center;
        padding: 0 16px;
    }
    .nav-link img {
        width: 24px;
        height: 24px;
        padding: 4px;
    }
    .nav-link span {
        padding: 8px;
    }
    .nav-links .profile {
        display: flex;
        align-items: center;
        gap: 12px; 
        padding: 0 16px;
    }
    .nav-links .profile img {
        width: 46px;
        height: 46px;
        border-radius: 50%;
        border: 0.5px solid #4D4D4D;
    }
    .nav-links .profile span {
        font-size: 18px;
        font-weight: 600;
        color: #4D4D4D;
    }
    @media (max-width: 600px) {
        .navbar {
            flex-direction: column;
            border-bottom: 1px dashed #EAEFF5;
            margin-left: 0;
            margin-right: 0;
        }

        .nav-links {
            margin-top: 10px;
        }
        .navbar * span {
            display: none !important;
        }
    }
</style>


<div class="navbar">
    <div class="logo">
        <img src="images/profile/company_logo.jpg" alt="Logo">
        <span>duggup</span>
    </div>
    <div class="nav-links">
        <div class="navigation">
            {#each navLinks as link}
                <a class="nav-link">
                    <img src={link.iconLink} alt={link.text}/>
                    <span>{link.text}</span>
                </a>
                        
            {/each}
        </div>
        <button class="raised-button nav-link">
            <img src="images/nav/post.svg" alt="Profile"/>
            <span>Post</span>
        </button>
        <div class="profile">
            <img src='images/profile/profile_pic.jpg' alt="Profile Picture"/>
            <span>Krishna Kiran</span>
            <i class="arrow down"></i>
        </div>
    </div>
</div>
