<template>
    <div>
        <header>
            <nav>
                <ul>
                    <li><NuxtLink to='/'>Home</NuxtLink></li>
                </ul>
            </nav>
        </header>

        <div>
            <slot/>
        </div>

        <footer>
            
        </footer>
    </div>
</template>

<style scoped>
    .router-link-exact-active {
        color: #12b488;
    }
</style>