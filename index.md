---
layout: default
---

<script src="https://cdn.rawgit.com/download/polymer-cdn/1.5.0/lib/webcomponentsjs/webcomponents-lite.min.js"></script>
<link href="https://maxcdn.bootstrapcdn.com/font-awesome/4.7.0/css/font-awesome.min.css" rel="stylesheet" integrity="sha384-wvfXpqpZZVQGK6TAh5PVlGOfQNHSoD2xbE+QkPxCAFlNEevoEH3Sl0sibVcOQVnN" crossorigin="anonymous">
<link rel="stylesheet" href="thirdparty/trackswitch-js/trackswitch.min.css" />
<script src="https://code.jquery.com/jquery-3.2.1.min.js" integrity="sha256-hwg4gsxgFZhOsEEamdOYGBf13FyQuiTwlAQgxVSNgt4=" crossorigin="anonymous"></script>
<script src="thirdparty/trackswitch-js/trackswitch.min.js"></script>
<script type="text/javascript">
    var settings = {
        onlyradiosolo: true,
        repeat: true,
    };

    jQuery(document).ready(function() {
        jQuery(".player").trackSwitch(settings); 
    });
</script>

# Direction-Preserving MIMO Speech Enhancement Using a Neural Covariance Estimator
This page presents binaural audio examples for the manuscript
> T. Deppisch, "Direction-Preserving MIMO Speech Enhancement Using a Neural Covariance Estimator", 2026.
The examples compare the clean target speech, the unprocessed noisy mixture, and enhanced signals obtained with an oracle direction-preserving MIMO Wiener filter (DP-MWF), a DP-MWF using covariance estimates from OnlineSpatialNet, and a DP-MWF using covariance estimates from NICE.

{% assign example_ids = "000000,000001,000002,000003,000004,000005,000006,000007,000008,000009" | split: "," %}
{% for example_id in example_ids %}
## Example {{ forloop.index0 }}

<div class="player">
    <ts-track title="Unprocessed Mixture">
        <ts-source src="audio/scene_{{ example_id }}_noisy_binaural.wav"></ts-source>
    </ts-track>
    <ts-track title="Clean Target">
        <ts-source src="audio/scene_{{ example_id }}_clean_binaural.wav"></ts-source>
    </ts-track>
    <ts-track title="Oracle DP-MWF">
        <ts-source src="audio/scene_{{ example_id }}_enhanced_binaural.wav"></ts-source>
    </ts-track>
    <ts-track title="OnlineSpatialNet + DP-MWF">
        <ts-source src="audio/OSN/scene_{{ example_id }}_enhanced_binaural.wav"></ts-source>
    </ts-track>
    <ts-track title="NICE + DP-MWF">
        <ts-source src="audio/NICE/scene_{{ example_id }}_enhanced_binaural.wav"></ts-source>
    </ts-track>
</div>

{% endfor %}
