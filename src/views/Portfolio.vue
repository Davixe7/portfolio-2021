<template>
  <div id="portfolio" style="padding-top: 30px">
    <div class="section-title">
      Proyectos Recientes
    </div>
    <div class="row">
      <div
        v-for="project in projects"
        :key="project.name"
        class="col-sm-6 col-lg-4">
        <div @click="currentProject=project; modal=true;">
          <project-card
          :project="project">
        </project-card>
        </div>
      </div>
    </div>
    <portfolio-modal
      v-show="modal"
      :project="currentProject"
      :nextEnabled="nextProjectIndex != null"
      :prevEnabled="prevProjectIndex != null"
      @goNext="currentProject=projects[nextProjectIndex]"
      @goPrev="currentProject=projects[prevProjectIndex]"
      @modalClosed="currentProject=null;modal=false;"
    /> 
  </div>
</template>

<script>
import PortfolioModal from '@/components/PortfolioModal'
import ProjectCard from '@/components/ProjectCard'

export default {
  components: {
    PortfolioModal,
    ProjectCard
  },
  computed:{
    prevProjectIndex(){
      if ( this.currentProjectIndex == null) return null;
      return this.currentProjectIndex != 0
             ? this.currentProjectIndex - 1
             : null
    },
    nextProjectIndex(){
      if ( this.currentProjectIndex == null) return null;
      return this.currentProjectIndex < this.projects.length - 1
             ? this.currentProjectIndex + 1
             : null
    },
    currentProjectIndex(){
      if( !this.currentProject ){ return null; }
      return this.projects.indexOf( this.currentProject )
    }
  },
  data(){return{
    currentProject: null,
    projects: [
      {
        name: 'Monsters PTY',
        url: 'https://monsters.pty',
        type: 'Tienda Online WooCommerce',
        description: "Monsters es una tienda online (un marketplace) de dise\u00f1o ubicada en ciudad de Panam\u00e1. Contamos con m\u00e1s de 40 marcas nacionales e internacionales, enfocado a personas que les gusta adquirir cosas diferentes y productos de calidad al mejor precio posible sin tener que salir de tu casa u oficina. Como sabemos que hay personas que les gusta probarse la ropa o ver las cosas f\u00edsicamente contamos tambi\u00e9n con un showroom ubicado en Calle 50.Monsters naci\u00f3 con el objetivo de crear un espacio o punto de venta online, donde marcas, artistas y dise\u00f1adores tanto paname\u00f1os como internacionales puedan vender susproductos a trav\u00e9s nuestra plataforma de compra online.Seleccionamos cuidadosamente las marcas o productos que traemos para ti y nos enfocamos siempre en brindarte la mejor experiencia de usuario posible.",
        captures: [
          'monsterspty.webp'
        ]
      },
      {
        name: 'Fukai',
        url: 'https://fukai.cl',
        type: 'Tienda Online Laravel',
        description: "PROPUESTA GASTRONO\u0301MICA Y EXPERIENCIA DE CLIENTE. Fukai es un restaurante de gastronomi\u0301a fusio\u0301n de diversas partes del mundo con una importante influencia de la cocina asia\u0301tica. A su reconocida oferta de sushi de autor se ha ido ampliando la oferta a cocina China, Tailandesa y Nikkei la cual con el paso del tiempo ha tenido gran aceptacio\u0301n por nuestros clientes, lo que ha favorecido a consolidar nuestra marca y posicionarnos como un restaurante reconocido por su amplia oferta, gran calidad y servicio. Como parte de nuestra oferta tambie\u0301n destaca una amplia gama de tragos y cockteleri\u0301a de autor.",
        captures: [
          'fukai.webp'
        ]
      },
      {
        name: 'Opinion US',
        url: 'https://opinion.us.com',
        type: 'Sitio Web Laravel',
        description: 'Just come take the survey',
        captures: [
          'opinionus.webp'
        ]
      },
      {
        name: 'PM Store',
        url: 'https://pmstore.com.ar',
        type: 'Tienda Online WooCommerce',
        description: "Te brindamos el mejor equipamiento comercial y para el hogar de segunda mano, al mejor precio.Contamos con stock propio pero lo que no tengamos nos lo ped\u00eds mediante el formulario de contacto y te lo conseguimos en menos de 5 d\u00edas.Nuestro principal servicio es encontrar lo que necesites y que ahorres una suma importante de dinero frente al costo de un producto nuevo, brind\u00e1ndote uno de segunda mano en la condici\u00f3n que necesites de acuerdo a tu presupuesto y con el objetivo de que logres las mismas prestaciones que con un producto nuevo.",
        captures: [
          'pmstore.webp'
        ]
      },
      {
        name: 'Restaurant Rosita',
        url: 'https://restaurantrosita.cl',
        type: 'Tienda Online Laravel',
        description: 'Todo comenzó con un viaje de nuestro chef Nicolás Rosen a tierras aztecas, en el cual queda fascinado por su gastronomía y su cultura, culminando en la creación de este lugar único en Santiago donde la música, el ambiente, la decoración traída especialmente de México y cada detalle se conjugan perfectamente para que tu estadía sea inolvidable. Los sabores de Rosita están compuestos por una diversidad de gastronomía mexicana y cocina Tex Mex (fusión Americana-Mexicana). Prepárate para disfrutar en pleno de esta propuesta que hemos preparado especialmente para ti.',
        captures: [
          'rosita.webp'
        ]
      },
      {
        name: 'Serendipia Flats',
        url: 'https://serendipiaflats.com',
        type: 'Sitio Web Laravel',
        description: 'Serendipia es un espacio creado para todos los amantes del lujo y la elegancia de manera asequible. Su ubicación estratégica en uno de los sectores más exclusivos de la capital de Colombia lo convierten en el lugar perfecto para jóvenes y extranjeros que deseen ser parte de una comunidad que disfruta de la experiencia de interactuar con su entorno, a través de la magia del diseño de sus espacios.',
        captures: [
          'serendipia.webp'
        ]
      },
      {
        name: 'Adsmarky',
        url: 'https://adsmarky.com',
        type: 'Tema Original WordPress',
        description: "We are a website that revolves around the new figure that has emerged with the emergence of social networks, INFLUENCER. Adsmarky.com born with the idea of bringing together on a single page the social content of the most influential people of different subjects without neglecting those who are beginning and that we believe that they can become social references for their Content and Quality.",
        captures: [
          'adsmarky.webp'
        ]
      },
      {
        name: 'FMDP',
        url: 'https://fundacionmdp.org',
        type: 'Tema Original WordPress',
        description: "La Fundaci\u00f3n Mutua de Propietarios es una instituci\u00f3n no lucrativa creada por la aseguradora Mutua de Propietarios con la misi\u00f3n de mejorar la accesibilidad de las personas con movilidad reducida, a la vivienda y a su entorno.Como parte de su compromiso con la Protecci\u00f3n y la Salud de la propiedad inmobiliaria, los seguros inmobiliarios y los servicios t\u00e9cnicos que ofrece Mutua de Propietarios tienen como objetivo cuidar de los edificios, de tu hogar, de tu negocio y, especialmente, de ti.",
        captures: [
          'fmdp.webp'
        ]
      },
      {
        name: 'Eligiendo Banco',
        url: 'https://eligiendobanco.com',
        type: 'Tema Original WordPress',
        description: "EL FEN\u00d3MENO DE LOS PR\u00c9STAMOS R\u00c1PIDOS ONLINE. Eligiendobanco.com quiere facilitar la tarea de elegir entre los distintos productos financieros ofreciendo una informaci\u00f3n clara y sencilla, que todo el mundo pueda entender y que agilice de la mayor manera posible el tramite a veces complicado de decidirse por el producto financiero que mejor se adapte a las necesidades de cada individuo.",
        captures: [
          'eligiendobanco.webp'
        ]
      },
    ],
    modal: false
  }}
}
</script>

<style lang="scss">
.main-banner.portfolio-banner {
  h1 {
    font-size: 34px;
  }
  .caption {
    font-size: 18px;
    line-height: 28px;
  }
}
</style>