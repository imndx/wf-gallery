<template>
    <div class="hello">
        <h1>野火产品截图展示</h1>
        <div v-for="(shot, index) in mobileScreenShots" :key="index" :id="index" class="shots-container">
            <h2 class="category">{{ shot.category }}</h2>
            <div class="mobile-images">
                <div :id="'lightgallery-mobile-' + index">
                    <a v-for="(url, i) in shot.images" :href="url" :key="i">
                        <img :alt="shot.category" :src="url"/>
                    </a>
                </div>
            </div>
        </div>
        <div v-for="(shot, index) in pcScreenShots" :key="mobileScreenShots.length + index" :id="mobileScreenShots.length + index" class="shots-container">
            <h2 class="category">{{ shot.category }}</h2>
            <div class="pc-images">
                <div :id="'lightgallery-pc-' + index">
                    <a v-for="(url, i) in shot.images" :href="url" :key="i">
                        <img :alt="shot.category" :src="url"/>
                    </a>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import 'lightgallery'
import 'lightgallery/css/lightgallery.css'
import lightGallery from "lightgallery";

export default {
    name: 'HelloWorld',
    data() {
        return {
            mobileScreenShots: [
                {
                    category: "Android端截图",
                    images: [
                        "http://static.wildfirechat.cn/android-view1.png",
                        "http://static.wildfirechat.cn/android-view2.png",
                        "http://static.wildfirechat.cn/android-view3.png",
                        "http://static.wildfirechat.cn/android-view4.png",
                        "http://static.wildfirechat.cn/android-view5.png",
                        "http://static.wildfirechat.cn/android-view6.png",
                        "http://static.wildfirechat.cn/android-view7.png",
                        "http://static.wildfirechat.cn/android-view8.png",
                        "http://static.wildfirechat.cn/android-view9.png",
                        "http://static.wildfirechat.cn/android-view10.png",
                        "http://static.wildfirechat.cn/android-view11.png",
                    ]
                },
                {
                    category: "iOS端截图",
                    images: [
                        "http://static.wildfirechat.cn/ios-message-view.png",
                        "http://static.wildfirechat.cn/ios-contact-view.png",
                        "http://static.wildfirechat.cn/ios-discover-view.png",
                        "http://static.wildfirechat.cn/ios-settings-view.png",
                        "http://static.wildfirechat.cn/ios-messagelist-view.png",
                        "http://static.wildfirechat.cn/ios-chat-setting-view.png",
                        "http://static.wildfirechat.cn/ios-takephoto-view.png",
                        "http://static.wildfirechat.cn/ios-record-voice-view.png",
                        "http://static.wildfirechat.cn/ios-location-view.png",
                        "http://static.wildfirechat.cn/ios-voip-view.png"
                    ]
                },
            ],
            pcScreenShots: [
                {
                    category: "PC端截图",
                    images: [
                        "http://static.wildfirechat.cn/ios-message-view.png",
                        "http://static.wildfirechat.cn/ios-contact-view.png",
                        "http://static.wildfirechat.cn/ios-discover-view.png",
                        "http://static.wildfirechat.cn/ios-settings-view.png",
                        "http://static.wildfirechat.cn/ios-messagelist-view.png",
                        "http://static.wildfirechat.cn/ios-chat-setting-view.png",
                        "http://static.wildfirechat.cn/ios-takephoto-view.png",
                        "http://static.wildfirechat.cn/ios-record-voice-view.png",
                        "http://static.wildfirechat.cn/ios-location-view.png",
                        "http://static.wildfirechat.cn/ios-voip-view.png"
                    ],
                },
                {
                    category: "Web端截图",
                    images: [
                        "http://static.wildfirechat.cn/ios-message-view.png",
                        "http://static.wildfirechat.cn/ios-contact-view.png",
                        "http://static.wildfirechat.cn/ios-discover-view.png",
                        "http://static.wildfirechat.cn/ios-settings-view.png",
                        "http://static.wildfirechat.cn/ios-messagelist-view.png",
                        "http://static.wildfirechat.cn/ios-chat-setting-view.png",
                        "http://static.wildfirechat.cn/ios-takephoto-view.png",
                        "http://static.wildfirechat.cn/ios-record-voice-view.png",
                        "http://static.wildfirechat.cn/ios-location-view.png",
                        "http://static.wildfirechat.cn/ios-voip-view.png"
                    ],
                },
                {
                    category: "管理后台截图",
                    images: [
                        "http://static.wildfirechat.cn/ios-message-view.png",
                        "http://static.wildfirechat.cn/ios-contact-view.png",
                        "http://static.wildfirechat.cn/ios-discover-view.png",
                        "http://static.wildfirechat.cn/ios-settings-view.png",
                        "http://static.wildfirechat.cn/ios-messagelist-view.png",
                        "http://static.wildfirechat.cn/ios-chat-setting-view.png",
                        "http://static.wildfirechat.cn/ios-takephoto-view.png",
                        "http://static.wildfirechat.cn/ios-record-voice-view.png",
                        "http://static.wildfirechat.cn/ios-location-view.png",
                        "http://static.wildfirechat.cn/ios-voip-view.png"
                    ],
                },
                {
                    category: "开发平台截图",
                    images: [
                        "http://static.wildfirechat.cn/ios-message-view.png",
                        "http://static.wildfirechat.cn/ios-contact-view.png",
                        "http://static.wildfirechat.cn/ios-discover-view.png",
                        "http://static.wildfirechat.cn/ios-settings-view.png",
                        "http://static.wildfirechat.cn/ios-messagelist-view.png",
                        "http://static.wildfirechat.cn/ios-chat-setting-view.png",
                        "http://static.wildfirechat.cn/ios-takephoto-view.png",
                        "http://static.wildfirechat.cn/ios-record-voice-view.png",
                        "http://static.wildfirechat.cn/ios-location-view.png",
                        "http://static.wildfirechat.cn/ios-voip-view.png"
                    ],
                },
                {
                    category: "频道管理系统截图",
                    images: [
                        "http://static.wildfirechat.cn/ios-message-view.png",
                        "http://static.wildfirechat.cn/ios-contact-view.png",
                        "http://static.wildfirechat.cn/ios-discover-view.png",
                        "http://static.wildfirechat.cn/ios-settings-view.png",
                        "http://static.wildfirechat.cn/ios-messagelist-view.png",
                        "http://static.wildfirechat.cn/ios-chat-setting-view.png",
                        "http://static.wildfirechat.cn/ios-takephoto-view.png",
                        "http://static.wildfirechat.cn/ios-record-voice-view.png",
                        "http://static.wildfirechat.cn/ios-location-view.png",
                        "http://static.wildfirechat.cn/ios-voip-view.png"
                    ],
                }
            ],
        }
    },

    mounted() {
        for (let i = 0; i < this.mobileScreenShots.length; i++) {
            const el = document.getElementById('lightgallery-mobile-' + i)
            lightGallery(el)
        }
        for (let i = 0; i < this.pcScreenShots.length; i++) {
            const el = document.getElementById('lightgallery-pc-' + i)
            lightGallery(el)
        }

        setTimeout(() => {
            const params = new URL(location.href).searchParams;
            let t = params.get('t');
            const el = document.getElementById("" + t);
            if (el) {
                el.scrollIntoView();
            }
        }, 500);
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.shots-container {
    display: flex;
    flex-direction: column;
}

.shots-container .category {
    font-size: 30px;
    /*color: red;*/
}

.shots-container .mobile-images {
    display: flex;
    justify-content: flex-start;
}

.shots-container .mobile-images img {
    width: 180px;
    height: 320px;
    margin: 10px;
}

.shots-container .pc-images img {
    width: 320px;
    height: 180px;
    margin: 10px;
}

</style>
