<template>
    <div class="hello">
        <h1>野火产品截图展示</h1>
        <div v-for="(shot, index) in mobileScreenShots" :key="index" :id="index" class="shots-container">
            <h2 class="category">{{ shot.category }}</h2>
            <div class="mobile-images">
                <div :id="'lightgallery-mobile-' + index" style="width: 100%">
                    <a v-for="(url, i) in shot.images" :href="url" :key="i">
                        <img :alt="shot.category" :src="url"/>
                    </a>
                </div>
            </div>
        </div>
        <div v-for="(shot, index) in pcScreenShots" :key="mobileScreenShots.length + index" :id="mobileScreenShots.length + index" class="shots-container">
            <h2 class="category">{{ shot.category }}</h2>
            <div class="pc-images">
                <div :id="'lightgallery-pc-' + index" style="width: 100%">
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
                        "https://static.wildfirechat.cn/android-view1.png",
                        "https://static.wildfirechat.cn/android-view2.png",
                        "https://static.wildfirechat.cn/android-view3.png",
                        "https://static.wildfirechat.cn/android-view4.png",
                        "https://static.wildfirechat.cn/android-view5.png",
                        "https://static.wildfirechat.cn/android-view6.png",
                        "https://static.wildfirechat.cn/android-view7.png",
                        "https://static.wildfirechat.cn/android-view8.png",
                        "https://static.wildfirechat.cn/android-view9.png",
                        "https://static.wildfirechat.cn/android-view10.png",
                        "https://static.wildfirechat.cn/android-view11.png",
                    ]
                },
                {
                    category: "iOS端截图",
                    images: [
                        "https://static.wildfirechat.cn/ios-message-view.png",
                        "https://static.wildfirechat.cn/ios-contact-view.png",
                        "https://static.wildfirechat.cn/ios-discover-view.png",
                        "https://static.wildfirechat.cn/ios-settings-view.png",
                        "https://static.wildfirechat.cn/ios-messagelist-view.png",
                        "https://static.wildfirechat.cn/ios-chat-setting-view.png",
                        "https://static.wildfirechat.cn/ios-takephoto-view.png",
                        "https://static.wildfirechat.cn/ios-record-voice-view.png",
                        "https://static.wildfirechat.cn/ios-location-view.png",
                        "https://static.wildfirechat.cn/ios-voip-view.png"
                    ]
                },
                {
                    category: "微信小程序端截图",
                    images: [
                        "https://static.wildfirechat.cn/wx-conversation_list.png",
                        "https://static.wildfirechat.cn/wx-conversation.png",
                        "https://static.wildfirechat.cn/wx-conversation_1.png",
                        "https://static.wildfirechat.cn/wx-friends.png",
                    ]
                },
                {
                    category: "uni-app端截图",
                    images: [
                        "https://static.wildfirechat.cn/uniapp_contact_tab.jpeg",
                        "https://static.wildfirechat.cn/uniapp_conversation.jpeg",
                        "https://static.wildfirechat.cn/uniapp_conversation_list.jpeg",
                        "https://static.wildfirechat.cn/uniapp_user_profile.jpeg",
                    ]
                },
            ],
            pcScreenShots: [
                {
                    category: "PC端截图",
                    images: [
                        "https://static.wildfirechat.cn/pc-home.png",
                        "https://static.wildfirechat.cn/pc-conversastion.png",
                        "https://static.wildfirechat.cn/pc-emoji.png",
                        "https://static.wildfirechat.cn/pc-contact.png",
                        "https://static.wildfirechat.cn/pc-channel.png",
                        "https://static.wildfirechat.cn/pc-fav.png",
                        "https://static.wildfirechat.cn/pc-file-history.png",
                        "https://static.wildfirechat.cn/pc-workspace.png",
                        "https://static.wildfirechat.cn/pc-setting.png",
                        "https://static.wildfirechat.cn/pc-multi-video-call.png",
                        "https://static.wildfirechat.cn/pc-multi-audio-call.png",

                    ],
                },
                {
                    category: "Web端截图",
                    images: [
                        "https://static.wildfirechat.cn/web-home.png",
                        "https://static.wildfirechat.cn/web-conversation.png",
                        "https://static.wildfirechat.cn/web-contact.png",
                        "https://static.wildfirechat.cn/web-channel.png",
                        "https://static.wildfirechat.cn/web-emoji.png",
                        "https://static.wildfirechat.cn/web-forward.png",
                        "https://static.wildfirechat.cn/web-setting.png",
                        "https://static.wildfirechat.cn/web-multi-video-call.png",
                        "https://static.wildfirechat.cn/web-multi-audio-call.png",
                    ],
                },
                {
                    category: "管理后台截图",
                    images: [
                        "https://static.wildfirechat.cn/admin-login.png",
                        "https://static.wildfirechat.cn/admin-home.png",
                        "https://static.wildfirechat.cn/admin-user-list.png",
                        "https://static.wildfirechat.cn/admin-blocked-list.png",
                        "https://static.wildfirechat.cn/admin-sensitive-word-list.png",
                        "https://static.wildfirechat.cn/admin-sensitive-word-match.png",
                        "https://static.wildfirechat.cn/admin-group-list.png",
                        "https://static.wildfirechat.cn/admin-message-list.png",
                        "https://static.wildfirechat.cn/admin-user-message-list.png",
                        "https://static.wildfirechat.cn/admin-broadcast.png",
                        "https://static.wildfirechat.cn/admin-multi-send.png",
                        "https://static.wildfirechat.cn/admin-robot-list.png",
                        "https://static.wildfirechat.cn/admin-channel-list.png",
                    ],
                },
                {
                    category: "开放平台截图",
                    images: [
                        "https://static.wildfirechat.cn/open-home.png",
                        "https://static.wildfirechat.cn/open-channel.png",
                        "https://static.wildfirechat.cn/open-robot.png",
                        "https://static.wildfirechat.cn/open-robot-create.png",
                    ],
                },
                {
                    category: "频道管理系统截图",
                    images: [
                        "https://static.wildfirechat.cn/channel-login.png",
                        "https://static.wildfirechat.cn/channel-channel-menu.png",
                        "https://static.wildfirechat.cn/channel-auto-reply.png",
                        "https://static.wildfirechat.cn/channel-account.png",
                        "https://static.wildfirechat.cn/channel-fans.png",
                        "https://static.wildfirechat.cn/channel-message.png",
                        "https://static.wildfirechat.cn/channel-article.png",
                        "https://static.wildfirechat.cn/channel-media.png",
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
