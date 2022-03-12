<template>
    <RplContainer>
        <rpl-row>
            <rpl-col cols=4 class="homeProductCardContainers">
                <rpl-card-content class="homeProductCards"
                    :link='{"text":"confidential","url":"/confidential"}'
                    :image='{"src":confidential,"focalPoint":{"x":"290","y":"170"},"width":580,"height":340}'
                    border
                    :center="false"
                    type="default"
                >
                    <div class="productCardLogoContainer">
                        <img style="vertical-align:middle" src="@/assets/confidential" height="50px">
                    </div>
                    
                    <div class="productCardDescription">
                        <p>
                            Latest information on confidential
                        </p>
                    </div>
                    
                    <p><b>I want to see the latest:</b></p>
                    <rpl-list class="titleHyperlink"
                        link=""
                        size="normal"
                        :iconScale="1"
                        iconColor="primary"
                        :list='[
                            {"symbol":"arrow_right_primary","link":"confidential","text":"confidential"},
                            {"symbol":"arrow_right_primary","link":"confidential","text":"confidential"},
                            {"symbol":"arrow_right_primary","link":"confidential","text":"confidential"}
                        ]'
                    />
                </rpl-card-content>
            </rpl-col>
            <rpl-col cols=4 class="homeProductCardContainers">
                <rpl-card-content class="homeProductCards"
                    :link='{"text":"confidential","url":"confidential"}'
                    :image='{"src":confidential,"focalPoint":{"x":"290","y":"170"},"width":580,"height":340}'
                    border
                    :center="false"
                    type="default"
                >
                    <div class="productCardLogoContainer">
                        <img style="vertical-align:middle" src="@/assets/confidential" height="55px">
                    </div>

                    <div class="productCardDescription">
                        <p>
                            confidential
                        </p>
                    </div>
        
                    <p><b>I want to see the latest:</b></p>
            
                    <rpl-list class="titleHyperlink"
                        link=""
                        size="normal"
                        :iconScale="1"
                        iconColor="primary"
                        :list='[
                            {"symbol":"arrow_right_primary","link":"confidential","text":"confidential"},
                            {"symbol":"arrow_right_primary","link":"confidential","text":"confidential"},
                            {"symbol":"arrow_right_primary","link":"confidential","text":"confidential"}
                        ]'
                    />
                </rpl-card-content>
            </rpl-col>
            <rpl-col cols=4 class="homeProductCardContainers">
                <rpl-card-content class="homeProductCards"
                    :link='{"text":"confidential","url":"confidential"}'
                    :image='{"src":confidential,"focalPoint":{"x":"290","y":"170"},"width":580,"height":340}'
                    border
                    :center="false"
                    type="default"
                >

                    <div class="productCardLogoContainer">
                        <img style="vertical-align:middle" src="confidential" height="55px">
                    </div>

                    <div class="productCardDescription">
                        <p>
                            confidential
                        </p>
                    </div>

                    <p><b>I want to see the latest:</b></p>
                    <rpl-list class="titleHyperlink"
                        link=""
                        size="normal"
                        :iconScale="1"
                        iconColor="primary"
                        :list='[
                            {"symbol":"arrow_right_primary","link":"confidential","text":"confidential"},
                            {"symbol":"arrow_right_primary","link":"confidential","text":"confidential"},
                            {"symbol":"arrow_right_primary","link":"confidential","text":"confidential"}
                        ]'
                    />
                </rpl-card-content>
            </rpl-col>
        </rpl-row>
    </RplContainer>
</template>

<script>
import { RplContainer, RplRow, RplCol } from '@dpc-sdp/ripple-grid'
import RplCardContent from '@dpc-sdp/ripple-card/CardContent'
import RplList from '@dpc-sdp/ripple-list'

export default {
    components: { RplContainer, RplRow, RplCol, RplCardContent, RplList },
    data: () => ({
        confidential: require('@/assets/confidential'),
        confidential: require('@/assets/confidential'),
        confidential: require('@/assets/confidential')
    })
}
</script>

<style>
    @import '../assets/productAndHomePages.css';
</style>
