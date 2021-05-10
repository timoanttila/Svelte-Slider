<script>
  import Gallery from './gallery.svelte';
  let images = [
    {
      image: "https://timoanttila.com/images/gallery/2018-deli-rumakuru-lapland.webp",
      alt: "Image Alt 1"
    }, {
      image: "https://timoanttila.com/images/gallery/20200922-deli-timo-nokia.webp",
      alt: "Image Alt 2"
    }
  ];
</script>

<Gallery images={images}/>
