<template>

    <div class="uk-form-horizontal">

        <template v-if="node.type === 'page'">
            <div class="uk-form-row">
                <span class="uk-form-label">{{ 'Title' | trans }}</span>
                <div class="uk-form-controls uk-form-controls-text">
                    <label><input type="checkbox" v-model="node.theme.title_hide"> {{ 'Hide Title' | trans }}</label>
                </div>
            </div>

            <div class="uk-form-row">
                <span class="uk-form-label">{{ 'Title Size' | trans }}</span>
                <div class="uk-form-controls uk-form-controls-text">
                    <label><input type="checkbox" v-model="node.theme.title_large"> {{ 'Extra large title.' | trans }}</label>
                </div>
            </div>

            <div class="uk-form-row">
                <span class="uk-form-label">{{ 'Alignment' | trans }}</span>
                <div class="uk-form-controls uk-form-controls-text">
                    <label><input type="checkbox" v-model="node.theme.alignment"> {{ 'Center the title and content.' | trans }}</label>
                </div>
            </div>
        </template>

        <div class="uk-form-row">
            <label for="form-class" class="uk-form-label">{{ 'HTML Class' | trans }}</label>
            <div class="uk-form-controls">
                <input id="form-class" class="uk-form-width-large" type="text" v-model="node.theme.html_class">
            </div>
        </div>

        <div class="uk-form-row">
            <span class="uk-form-label">{{ 'Sidebar' | trans }}</span>
            <div class="uk-form-controls uk-form-controls-text">
                <label><input type="checkbox" v-model="node.theme.sidebar_first"> {{ 'Show the sidebar before the content.' | trans }}</label>
            </div>
        </div>

        <div class="uk-form-row">
            <label class="uk-form-label">Hero {{ 'Position' | trans }}</label>
            <div class="uk-form-controls uk-form-controls-text">
                <p class="uk-form-controls-condensed">
                    <label><input type="checkbox" v-model="node.theme.hero_viewport"> {{ 'Full viewport height' | trans }}</label>
                </p>
                <p class="uk-form-controls-condensed">
                    <label><input type="checkbox" v-model="node.theme.hero_contrast"> {{ 'Invert colors' | trans }}</label>
                </p>
                <p class="uk-form-controls-condensed uk-margin-bottom">
                    <label><input type="checkbox" v-model="node.theme.hero_parallax"> {{ 'Enable parallax effect' | trans }}</label>
                </p>
                <p class="uk-form-controls-condensed uk-form-width-large"><input-image :source.sync="node.theme.hero_image"></input-image></p>
                <p class="uk-form-help-block">{{ 'Select a background image for the hero position.' | trans }}</p>
            </div>
        </div>

        <div class="uk-form-row">
            <span class="uk-form-label">{{ 'Content Top Padding' | trans }}</span>
            <div class="uk-form-controls uk-form-controls-text">
                <label><input type="checkbox" v-model="node.theme.content_top_padding"> {{ 'Remove the padding (whitespace) from the layout position for rimless content display.' | trans }}</label>
            </div>
        </div>

        <div class="uk-form-row">
            <span class="uk-form-label">{{ 'Content Bottom Padding' | trans }}</span>
            <div class="uk-form-controls uk-form-controls-text">
                <label><input type="checkbox" v-model="node.theme.content_bottom_padding"> {{ 'Remove the padding (whitespace) from the layout position for rimless content display.' | trans }}</label>
            </div>
        </div>

    </div>

</template>

<script>

    module.exports = {

        section: {
            label: 'Theme',
            priority: 90
        },

        props: ['node']

    };

    window.Site.components['node-theme'] = module.exports;

</script>
