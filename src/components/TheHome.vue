<script setup>
</script>

<template>
  <ContentItem>
    <p>
      <iframe
          src="https://player.twitch.tv/?channel=matthmoica&parent=localhost"
          height="500"
          width="100%"
          frameborder="0"
          allowfullscreen>
      </iframe>
    </p>
    <p>
      Dernières vidéos
      <iframe width="560" 
        height="315" 
        src="https://www.youtube.com/embed/DxVV_fpCCtI?si=0CDdZmCIpA7IX5G4" 
        frameborder="0" 
        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" 
        referrerpolicy="strict-origin-when-cross-origin" 
        allowfullscreen>
      </iframe>
    </p>

    <iframe src="https://discord.com/widget?id=1230866705572565052&theme=dark" width="350" height="500" allowtransparency="true" frameborder="0" sandbox="allow-popups allow-popups-to-escape-sandbox allow-same-origin allow-scripts"></iframe>
  </ContentItem>
</template>
