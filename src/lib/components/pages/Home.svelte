<script>
  import {
    Hero,
    Reviews,
    TicketCarousel,
    HowItWorks,
    HeadLine,
    WhatWeDo,
    GiftCard,
    Bubbles,
  } from '$lib/index'
  import { onMount } from 'svelte'
  export let items
  export let itemCollection

  onMount(() => {
    const bubbles = document.querySelectorAll('.bubble')

    bubbles.forEach((bubble, index) => {
      bubble.style.setProperty('--i', index + 1)
    })
  })
</script>

<svelte:head>
  <title>{items[0].title}</title>
</svelte:head>
<section>
  <Hero {items} />
  <Reviews {items} />
  <TicketCarousel {itemCollection} />
  <HeadLine title="How It Works" />
  <HowItWorks {items} />
  <HeadLine title="What We Do" />
  <WhatWeDo {items} />
  <GiftCard items={items[3]} />
  <div class="bubbles1">
    <Bubbles />
  </div>
  <svg
    version="1.1"
    class="glas1"
    id="Layer_1"
    xmlns="http://www.w3.org/2000/svg"
    xmlns:xlink="http://www.w3.org/1999/xlink"
    viewBox="0 0 361.397 361.397"
    xml:space="preserve"
    fill="#000000"
    ><g id="SVGRepo_bgCarrier" stroke-width="0"></g><g
      id="SVGRepo_tracerCarrier"
      stroke-linecap="round"
      stroke-linejoin="round"
      stroke="#CCCCCC"
      stroke-width="0.722794"
    ></g><g id="SVGRepo_iconCarrier">
      <g id="XMLID_1103_">
        <g id="XMLID_1106_">
          <g id="XMLID_1105_">
            <rect
              id="XMLID_61_"
              x="208.47"
              y="1.246"
              transform="matrix(-0.9766 -0.2151 0.2151 -0.9766 423.2374 171.8619)"
              style="fill:#2CB79A;"
              width="25"
              height="123.313"
            ></rect>
          </g>
        </g>
        <g id="XMLID_1107_">
          <polygon
            id="XMLID_57_"
            style="fill:#1DD2A5;"
            points="147.076,126.508 167.05,118.521 125.316,14.16 58.011,15.042 58.292,36.552 110.827,35.863 "
          ></polygon>
        </g>
        <g id="XMLID_1108_">
          <g id="XMLID_1109_">
            <path
              id="XMLID_1112_"
              style="fill:#C1E8E6;"
              d="M41.521,96.412L180.698,235.59L319.876,96.412 c5.088-5.088,1.484-13.787-5.711-13.787H47.231C40.037,82.625,36.433,91.324,41.521,96.412z"
            ></path>
            <path
              id="XMLID_1115_"
              style="fill:#A0CFF1;"
              d="M314.165,82.625H180.698v152.964L319.876,96.412 C324.963,91.324,321.36,82.625,314.165,82.625z"
            ></path>
          </g>
          <g id="XMLID_1116_">
            <path
              id="XMLID_46_"
              style="fill:#C1E8E6;"
              d="M235.531,348.972l-54.832-27.599l-54.832,27.599 c-5.477,3.823-2.772,12.425,3.907,12.425h101.851C238.303,361.397,241.008,352.795,235.531,348.972z"
            ></path>
            <path
              id="XMLID_1120_"
              style="fill:#A0CFF1;"
              d="M235.531,348.972l-54.832-27.599v40.024h50.925 C238.303,361.397,241.008,352.795,235.531,348.972z"
            ></path>
          </g>
          <g id="XMLID_1121_">
            <rect
              id="XMLID_39_"
              x="167.05"
              y="165.981"
              style="fill:#C1E8E6;"
              width="27.297"
              height="164.905"
            ></rect>
            <rect
              id="XMLID_1125_"
              x="180.698"
              y="165.981"
              style="fill:#A0CFF1;"
              width="13.649"
              height="164.905"
            ></rect>
          </g>
        </g>
        <g id="XMLID_1126_">
          <polygon
            id="XMLID_1127_"
            style="fill:#f962ed;"
            points="91.475,124.549 180.698,213.772 269.921,124.549 "
          ></polygon>
          <polygon
            id="XMLID_1128_"
            style="fill:#d73cd2;"
            points="180.698,124.549 180.698,213.772 269.921,124.549 "
          ></polygon>
        </g>
      </g>
    </g></svg
  >
  <div class="bubbles2">
    <Bubbles />
  </div>
  <svg
    version="1.1"
    class="glas2"
    id="Layer_1"
    xmlns="http://www.w3.org/2000/svg"
    xmlns:xlink="http://www.w3.org/1999/xlink"
    viewBox="0 0 361.397 361.397"
    xml:space="preserve"
    fill="#000000"
    ><g id="SVGRepo_bgCarrier" stroke-width="0"></g><g
      id="SVGRepo_tracerCarrier"
      stroke-linecap="round"
      stroke-linejoin="round"
      stroke="#CCCCCC"
      stroke-width="0.722794"
    ></g><g id="SVGRepo_iconCarrier">
      <g id="XMLID_1103_">
        <g id="XMLID_1106_">
          <g id="XMLID_1105_">
            <rect
              id="XMLID_61_"
              x="208.47"
              y="1.246"
              transform="matrix(-0.9766 -0.2151 0.2151 -0.9766 423.2374 171.8619)"
              style="fill:#3d2db9;"
              width="25"
              height="123.313"
            ></rect>
          </g>
        </g>
        <g id="XMLID_1107_">
          <polygon
            id="XMLID_57_"
            style="fill:#1d41d3;"
            points="147.076,126.508 167.05,118.521 125.316,14.16 58.011,15.042 58.292,36.552 110.827,35.863 "
          ></polygon>
        </g>
        <g id="XMLID_1108_">
          <g id="XMLID_1109_">
            <path
              id="XMLID_1112_"
              style="fill:#C1E8E6;"
              d="M41.521,96.412L180.698,235.59L319.876,96.412 c5.088-5.088,1.484-13.787-5.711-13.787H47.231C40.037,82.625,36.433,91.324,41.521,96.412z"
            ></path>
            <path
              id="XMLID_1115_"
              style="fill:#A0CFF1;"
              d="M314.165,82.625H180.698v152.964L319.876,96.412 C324.963,91.324,321.36,82.625,314.165,82.625z"
            ></path>
          </g>
          <g id="XMLID_1116_">
            <path
              id="XMLID_46_"
              style="fill:#C1E8E6;"
              d="M235.531,348.972l-54.832-27.599l-54.832,27.599 c-5.477,3.823-2.772,12.425,3.907,12.425h101.851C238.303,361.397,241.008,352.795,235.531,348.972z"
            ></path>
            <path
              id="XMLID_1120_"
              style="fill:#A0CFF1;"
              d="M235.531,348.972l-54.832-27.599v40.024h50.925 C238.303,361.397,241.008,352.795,235.531,348.972z"
            ></path>
          </g>
          <g id="XMLID_1121_">
            <rect
              id="XMLID_39_"
              x="167.05"
              y="165.981"
              style="fill:#C1E8E6;"
              width="27.297"
              height="164.905"
            ></rect>
            <rect
              id="XMLID_1125_"
              x="180.698"
              y="165.981"
              style="fill:#A0CFF1;"
              width="13.649"
              height="164.905"
            ></rect>
          </g>
        </g>
        <g id="XMLID_1126_">
          <polygon
            id="XMLID_1127_"
            style="fill:#34da74;"
            points="91.475,124.549 180.698,213.772 269.921,124.549 "
          ></polygon>
          <polygon
            id="XMLID_1128_"
            style="fill:#2cba35;"
            points="180.698,124.549 180.698,213.772 269.921,124.549 "
          ></polygon>
        </g>
      </g>
    </g></svg
  >
  <div class="bubbles3">
    <Bubbles />
  </div>
  <svg
    version="1.1"
    class="glas3"
    id="Layer_1"
    xmlns="http://www.w3.org/2000/svg"
    xmlns:xlink="http://www.w3.org/1999/xlink"
    viewBox="0 0 361.397 361.397"
    xml:space="preserve"
    fill="#000000"
    ><g id="SVGRepo_bgCarrier" stroke-width="0"></g><g
      id="SVGRepo_tracerCarrier"
      stroke-linecap="round"
      stroke-linejoin="round"
      stroke="#CCCCCC"
      stroke-width="0.722794"
    ></g><g id="SVGRepo_iconCarrier">
      <g id="XMLID_1103_">
        <g id="XMLID_1106_">
          <g id="XMLID_1105_">
            <rect
              id="XMLID_61_"
              x="208.47"
              y="1.246"
              transform="matrix(-0.9766 -0.2151 0.2151 -0.9766 423.2374 171.8619)"
              style="fill:#32b34c;"
              width="25"
              height="123.313"
            ></rect>
          </g>
        </g>
        <g id="XMLID_1107_">
          <polygon
            id="XMLID_57_"
            style="fill:#44d31d;"
            points="147.076,126.508 167.05,118.521 125.316,14.16 58.011,15.042 58.292,36.552 110.827,35.863 "
          ></polygon>
        </g>
        <g id="XMLID_1108_">
          <g id="XMLID_1109_">
            <path
              id="XMLID_1112_"
              style="fill:#C1E8E6;"
              d="M41.521,96.412L180.698,235.59L319.876,96.412 c5.088-5.088,1.484-13.787-5.711-13.787H47.231C40.037,82.625,36.433,91.324,41.521,96.412z"
            ></path>
            <path
              id="XMLID_1115_"
              style="fill:#A0CFF1;"
              d="M314.165,82.625H180.698v152.964L319.876,96.412 C324.963,91.324,321.36,82.625,314.165,82.625z"
            ></path>
          </g>
          <g id="XMLID_1116_">
            <path
              id="XMLID_46_"
              style="fill:#C1E8E6;"
              d="M235.531,348.972l-54.832-27.599l-54.832,27.599 c-5.477,3.823-2.772,12.425,3.907,12.425h101.851C238.303,361.397,241.008,352.795,235.531,348.972z"
            ></path>
            <path
              id="XMLID_1120_"
              style="fill:#A0CFF1;"
              d="M235.531,348.972l-54.832-27.599v40.024h50.925 C238.303,361.397,241.008,352.795,235.531,348.972z"
            ></path>
          </g>
          <g id="XMLID_1121_">
            <rect
              id="XMLID_39_"
              x="167.05"
              y="165.981"
              style="fill:#C1E8E6;"
              width="27.297"
              height="164.905"
            ></rect>
            <rect
              id="XMLID_1125_"
              x="180.698"
              y="165.981"
              style="fill:#A0CFF1;"
              width="13.649"
              height="164.905"
            ></rect>
          </g>
        </g>
        <g id="XMLID_1126_">
          <polygon
            id="XMLID_1127_"
            style="fill:#da3434;"
            points="91.475,124.549 180.698,213.772 269.921,124.549 "
          ></polygon>
          <polygon
            id="XMLID_1128_"
            style="fill:#ba2c2c;"
            points="180.698,124.549 180.698,213.772 269.921,124.549 "
          ></polygon>
        </g>
      </g>
    </g></svg
  >
  <div class="bubbles4">
    <Bubbles />
  </div>
  <svg
    version="1.1"
    class="glas4"
    id="Layer_1"
    xmlns="http://www.w3.org/2000/svg"
    xmlns:xlink="http://www.w3.org/1999/xlink"
    viewBox="0 0 361.397 361.397"
    xml:space="preserve"
    fill="#000000"
    ><g id="SVGRepo_bgCarrier" stroke-width="0"></g><g
      id="SVGRepo_tracerCarrier"
      stroke-linecap="round"
      stroke-linejoin="round"
      stroke="#CCCCCC"
      stroke-width="0.722794"
    ></g><g id="SVGRepo_iconCarrier">
      <g id="XMLID_1103_">
        <g id="XMLID_1106_">
          <g id="XMLID_1105_">
            <rect
              id="XMLID_61_"
              x="208.47"
              y="1.246"
              transform="matrix(-0.9766 -0.2151 0.2151 -0.9766 423.2374 171.8619)"
              style="fill:#2CB79A;"
              width="25"
              height="123.313"
            ></rect>
          </g>
        </g>
        <g id="XMLID_1107_">
          <polygon
            id="XMLID_57_"
            style="fill:#1DD2A5;"
            points="147.076,126.508 167.05,118.521 125.316,14.16 58.011,15.042 58.292,36.552 110.827,35.863 "
          ></polygon>
        </g>
        <g id="XMLID_1108_">
          <g id="XMLID_1109_">
            <path
              id="XMLID_1112_"
              style="fill:#C1E8E6;"
              d="M41.521,96.412L180.698,235.59L319.876,96.412 c5.088-5.088,1.484-13.787-5.711-13.787H47.231C40.037,82.625,36.433,91.324,41.521,96.412z"
            ></path>
            <path
              id="XMLID_1115_"
              style="fill:#A0CFF1;"
              d="M314.165,82.625H180.698v152.964L319.876,96.412 C324.963,91.324,321.36,82.625,314.165,82.625z"
            ></path>
          </g>
          <g id="XMLID_1116_">
            <path
              id="XMLID_46_"
              style="fill:#C1E8E6;"
              d="M235.531,348.972l-54.832-27.599l-54.832,27.599 c-5.477,3.823-2.772,12.425,3.907,12.425h101.851C238.303,361.397,241.008,352.795,235.531,348.972z"
            ></path>
            <path
              id="XMLID_1120_"
              style="fill:#A0CFF1;"
              d="M235.531,348.972l-54.832-27.599v40.024h50.925 C238.303,361.397,241.008,352.795,235.531,348.972z"
            ></path>
          </g>
          <g id="XMLID_1121_">
            <rect
              id="XMLID_39_"
              x="167.05"
              y="165.981"
              style="fill:#C1E8E6;"
              width="27.297"
              height="164.905"
            ></rect>
            <rect
              id="XMLID_1125_"
              x="180.698"
              y="165.981"
              style="fill:#A0CFF1;"
              width="13.649"
              height="164.905"
            ></rect>
          </g>
        </g>
        <g id="XMLID_1126_">
          <polygon
            id="XMLID_1127_"
            style="fill:#f962ed;"
            points="91.475,124.549 180.698,213.772 269.921,124.549 "
          ></polygon>
          <polygon
            id="XMLID_1128_"
            style="fill:#d73cd2;"
            points="180.698,124.549 180.698,213.772 269.921,124.549 "
          ></polygon>
        </g>
      </g>
    </g></svg
  >
</section>

<style>
  section {
    height: 100%;
    width: 100vw;
  }
  .glas1,
  .glas2,
  .glas3,
  .glas4 {
    position: absolute;
    width: 12rem;
    top: 870%;
  }
  .glas1 {
    left: 0;
  }
  .glas2 {
    left: 18rem;
  }
  .glas3 {
    right: 18rem;
  }
  .glas4 {
    right: 0rem;
  }
  .bubbles1,
  .bubbles2,
  .bubbles3,
  .bubbles4 {
    position: absolute;
    width: 12rem;
    height: 600%;
  }
  .bubbles1 {
    left: 0;
  }
  .bubbles2 {
    left: 18rem;
  }
  .bubbles3 {
    right: 18rem;
  }
  .bubbles4 {
    right: 0;
  }
  svg {
    animation: animate-in-and-out;
    animation-timeline: view();
  }
  @keyframes animate-in-and-out {
    entry 0% {
      opacity: 0;
      transform: translateY(100%);
    }
    entry 100% {
      opacity: 1;
      transform: translateY(0);
    }

    exit 0% {
      opacity: 1;
      transform: translateY(0);
    }
    exit 100% {
      opacity: 0;
      transform: translateY(-100%);
    }
  }
</style>
