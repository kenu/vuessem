<template>
  <div id="app">
    <img id="logo" alt="Vue logo" src="./assets/logo.png" />

    <h5>Alert</h5>
    <b-alert show>Primary Alert</b-alert>

    <h5>Badge</h5>
    <h6>
      Example heading
      <b-badge>New</b-badge>
    </h6>

    <h5>Breadcrumb</h5>
    <b-breadcrumb :items="items"></b-breadcrumb>

    <h5>Button</h5>
    <b-button>Button</b-button>

    <h5>Button Group</h5>
    <b-button-group>
      <b-button>Button 1</b-button>
      <b-button>Button 2</b-button>
      <b-button>Button 3</b-button>
    </b-button-group>

    <h5>Button Toolbar</h5>
    <b-button-toolbar key-nav aria-label="Toolbar with button groups">
      <b-button-group class="mx-1">
        <b-button>&laquo;</b-button>
        <b-button>&lsaquo;</b-button>
      </b-button-group>
      <b-button-group class="mx-1">
        <b-button>Edit</b-button>
        <b-button>Undo</b-button>
        <b-button>Redo</b-button>
      </b-button-group>
      <b-button-group class="mx-1">
        <b-button>&rsaquo;</b-button>
        <b-button>&raquo;</b-button>
      </b-button-group>
    </b-button-toolbar>

    <h5>Card</h5>
    <b-card
      title="Card Title"
      img-src="https://picsum.photos/600/300/?image=25"
      img-alt="Image"
      img-top
      tag="article"
      style="max-width: 20rem;"
      class="mb-2"
    >
      <b-card-text>Some quick example text to build on the card title and make up the bulk of the card's content.</b-card-text>

      <b-button href="#" variant="primary">Go somewhere</b-button>
    </b-card>

    <h5>Carousel</h5>
    <div>
      <b-carousel
        id="carousel-1"
        v-model="slide"
        :interval="3000"
        controls
        indicators
        background="#ababab"
        img-width="1024"
        img-height="480"
        style="text-shadow: 1px 1px 2px #333;"
        @sliding-start="onSlideStart"
        @sliding-end="onSlideEnd"
      >
        <!-- Text slides with image -->
        <b-carousel-slide
          caption="First slide"
          text="Nulla vitae elit libero, a pharetra augue mollis interdum."
          img-src="https://picsum.photos/1024/480/?image=52"
        ></b-carousel-slide>

        <!-- Slides with custom text -->
        <b-carousel-slide img-src="https://picsum.photos/1024/480/?image=54">
          <h1>Hello world!</h1>
        </b-carousel-slide>

        <!-- Slides with image only -->
        <b-carousel-slide img-src="https://picsum.photos/1024/480/?image=58"></b-carousel-slide>

        <!-- Slides with img slot -->
        <!-- Note the classes .d-block and .img-fluid to prevent browser default image alignment -->
        <b-carousel-slide>
          <template v-slot:img>
            <img
              class="d-block img-fluid w-100"
              width="1024"
              height="480"
              src="https://picsum.photos/1024/480/?image=55"
              alt="image slot"
            />
          </template>
        </b-carousel-slide>

        <!-- Slide with blank fluid image to maintain slide aspect ratio -->
        <b-carousel-slide caption="Blank Image" img-blank img-alt="Blank image">
          <p>
            Lorem ipsum dolor sit amet, consectetur adipiscing elit. Suspendisse eros felis, tincidunt
            a tincidunt eget, convallis vel est. Ut pellentesque ut lacus vel interdum.
          </p>
        </b-carousel-slide>
      </b-carousel>

      <p class="mt-4">
        Slide #: {{ slide }}
        <br />
        Sliding: {{ sliding }}
      </p>
    </div>

    <h5>Collapse</h5>
    <b-button v-b-toggle.collapse-1 variant="primary">Toggle Collapse</b-button>
    <b-collapse id="collapse-1" class="mt-2">
      <b-card>
        <p class="card-text">Collapse contents Here</p>
        <b-button v-b-toggle.collapse-1-inner size="sm">Toggle Inner Collapse</b-button>
        <b-collapse id="collapse-1-inner" class="mt-2">
          <b-card>Hello!</b-card>
        </b-collapse>
      </b-card>
    </b-collapse>

    <h5>Dropdown</h5>
    <b-dropdown id="dropdown-1" text="Dropdown Button" class="m-md-2">
      <b-dropdown-item>First Action</b-dropdown-item>
      <b-dropdown-item>Second Action</b-dropdown-item>
      <b-dropdown-item>Third Action</b-dropdown-item>
      <b-dropdown-divider></b-dropdown-divider>
      <b-dropdown-item active>Active action</b-dropdown-item>
      <b-dropdown-item disabled>Disabled action</b-dropdown-item>
    </b-dropdown>

    <h5>Embed</h5>
    <b-embed
      type="iframe"
      aspect="16by9"
      src="https://www.youtube.com/embed/zpOULjyy-n8?rel=0"
      allowfullscreen
    ></b-embed>

    <h5>Form</h5>
    <h5>Form Checkbox</h5>
    <h5>Form File</h5>
    <h5>Form Group</h5>
    <h5>Form Input</h5>
    <h5>Form Radio</h5>
    <h5>Form Select</h5>
    <h5>Form Textarea</h5>
    <h5>Image</h5>
    <h5>Input Group</h5>
    <h5>Jumbotron</h5>
    <h5>Layout and Grid System</h5>
    <h5>Link</h5>
    <h5>List group</h5>
    <h5>Media</h5>
    <h5>Modal</h5>
    <h5>Nav</h5>
    <h5>Navbar</h5>
    <h5>Pagination</h5>
    <h5>Pagination Nav</h5>
    <h5>Popover</h5>
    <h5>Progress</h5>
    <h5>Spinner</h5>
    <h5>Table</h5>
    <h5>Tabs</h5>
    <h5>Toasts</h5>
    <h5>Tooltip</h5>
  </div>
</template>

<script>
export default {
  name: "app",
  data() {
    return {
      items: [
        {
          text: "Admin",
          href: "#"
        },
        {
          text: "Manage",
          href: "#"
        },
        {
          text: "Library",
          active: true
        }
      ],
      slide: 0,
      sliding: null
    };
  },
  methods: {
    onSlideStart() {
      this.sliding = true;
    },
    onSlideEnd() {
      this.sliding = false;
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 30px;
}

#logo {
  width: 50px;
}

.card-img-top {
  width: 100%;
  border-top-left-radius: calc(0.25rem - 1px);
  border-top-right-radius: calc(0.25rem - 1px);
}
</style>
