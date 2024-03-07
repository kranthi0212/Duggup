<script>
    import Profile from './Profile.svelte';
    import Timeline from './Timeline.svelte';
    import { FaHome, FaCompass, FaBookOpen, FaEdit } from 'svelte-icons/fa';
    let navLinks = [
        { text: 'Home', icon: FaHome },
        { text: 'Explore', icon: FaCompass },
        { text: 'Learn', icon: FaBookOpen },
        { text: 'Post', icon: FaEdit }
    ];
</script>

<style>
    .navbar {
        display: flex;
        align-items: center;
        justify-content: space-between;
        padding: 10px;
        background-color: white; 
        color: #4D4D4D;
    }

    .nav-links {
        display: flex;
        align-items: center;
        gap: 10px;
    }

    .nav-links a {
        color: #4D4D4D; 
        text-decoration: none;
    }

    .nav-links a:hover {
        text-decoration: underline;
    }

    .logo img {
        width: 40px;
        height: 40px;
        border-radius: 50%;
    }

    @media (max-width: 600px) {
        .navbar {
            flex-direction: column;
        }

        .nav-links {
            margin-top: 10px;
        }
    }
</style>


<div class="navbar">
    <div class="logo">
        <!-- Replace 'logo.jpg' with your own image -->
        <img src="https://media.licdn.com/dms/image/D560BAQFHRBPTiTkqnA/company-logo_100_100/0/1687508146558/duggup_logo?e=1717632000&v=beta&t=xSqWU_IIJJTtXYzh2q7PTIulC5u7gsDwdq36CcPnU4U" alt="Logo">
    </div>
    <div class="nav-links">
        {#each navLinks as link}
            <a href="#"><link.icon /> {link.text}</a>
        {/each}
    </div>
</div>
<Profile />
<Timeline />