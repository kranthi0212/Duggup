<!-- Profile.svelte -->
<script>
    // No script needed for this component
</script>

<style>
    .profile {
        display: flex;
        align-items: center;
        justify-content: center;
        gap: 10px;
        margin-top: 20px;
        padding: 20px 120px; 
    }

    .profile img {
        width: 120px;
        height: 120px;
        border-radius: 50%;
        border: 5px solid #EAEFF5;
    }

    .profile p {
        font-size: 14px;
        font-style: inter;
        color: #4D4D4D;
        margin: 0;
        max-width: 584px; 
        height: 72px; 
    }
</style>

<div class="profile">
    <img src='https://media.licdn.com/dms/image/D4E03AQF-fLP5TtdtOQ/profile-displayphoto-shrink_400_400/0/1677089436637?e=1715212800&v=beta&t=J9-kSXKFOUgtVi6XPQhaWVHz74by4_pPnILLu6S3S6Y' alt="Profile Picture"/>
    <p>
        Co-Founder and CEO at Duggup - Social network for people in tech. Ex-Amazon Head of Engineering. I write hot-takes on building a business, shipping delightful products and accelerating product and career growth.
    </p>
</div>
