<template>
    <div class="scroll-to-top">
        <transition name="fade-up-transition" appear>
            <button v-if="show" href="#__nuxt" class="btn bg-pink-500 text-white hover:bg-pink-600 rounded-full inline-flex items-center justify-center transform active:scale-95 transition duration-100 ease-linear" v-smooth-scroll>
                <svg class="w-6 h-6" fill="#ec4899" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 11l7-7 7 7M5 19l7-7 7 7"></path></svg>
            </button>
        </transition>
    </div>
</template>

<script>
export default {
    data(){
        return {
            show: false,
            active: false,
        }
    },
    methods: {
        scrollToTop(){
            window.scroll({top: 0, behavior: 'smooth'});
            this.active = true;
            window.setTimeout(()=>{
              this.active = false;
            }, 1500);
        },
        toggleShow(){
            const el = document.documentElement,
                scrollTop = el.scrollTop;
            if (scrollTop > 500){
                this.show = true;
            }else{
                this.show = false;
            }
        },
        addScrollListener(){
            const self = this;
            window.addEventListener("scroll", ()=>{
                self.toggleShow();
            });
        }
    },
    mounted(){
        this.addScrollListener();
    }
}
</script>

<style lang="css" scoped>
.scroll-to-top{
    position: fixed;
    bottom: 1rem;
    right: 1rem;
    z-index: 15;
}
.scroll-to-top .btn{
    width: 30px;
    height: 30px;
    box-shadow: 0px 1px 7px 1px rgba(0, 0, 0, 0.101562);
}
</style>
