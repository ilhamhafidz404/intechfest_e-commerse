<script setup>
//
import Navbar from "../components/navbar/navbar.vue";
import Footer from "../components/footer.vue";
//
import ProductCard from "../components/productCard.vue";
//
import { Button } from "flowbite-vue";

// icons
import FilterIcon from "../components/icons/filterIcon.vue";
import ChevronDownIcon from "../components/icons/chevronDownIcon.vue";
import SortByIcon from "../components/icons/sortByIcon.vue";

const products = [
  {
    dataFilter: "laptop",
    img: "/src/assets/product/laptop/1.webp",
    isDiscount: true,
    isPopular: false,
    isNew: false,
    hasColors: false,
    isFlashSale: false,
    name: "Laptop ALOPE IL 14",
  },
  {
    dataFilter: "laptop",
    img: "/src/assets/product/laptop/2.webp",
    isDiscount: false,
    isPopular: true,
    isNew: false,
    hasColors: true,
    isFlashSale: false,
    name: "Laptop ALOPE IL 14 PRO",
  },
  {
    dataFilter: "laptop",
    img: "/src/assets/product/laptop/3.webp",
    isDiscount: false,
    isPopular: false,
    isNew: false,
    hasColors: false,
    isFlashSale: false,
    name: "ALOPE Notebook S4T",
  },
  {
    dataFilter: "handphone",
    img: "/src/assets/product/phone/3.webp",
    isDiscount: false,
    isPopular: false,
    isNew: false,
    hasColors: false,
    isFlashSale: false,
    name: "ALOPE Phone Ultron",
  },
  {
    dataFilter: "handphone",
    img: "/src/assets/product/phone/2.webp",
    isDiscount: false,
    isPopular: false,
    isNew: false,
    hasColors: false,
    isFlashSale: false,
    name: "ALOPE Galaxy Wings",
  },
  {
    dataFilter: "monitor",
    img: "/src/assets/product/monitor/1.webp",
    isDiscount: false,
    isPopular: false,
    isNew: true,
    hasColors: false,
    isFlashSale: false,
    name: "ALOPE Monitor 14inc",
  },
  {
    dataFilter: "monitor",
    img: "/src/assets/product/monitor/2.webp",
    isDiscount: false,
    isPopular: false,
    isNew: false,
    hasColors: false,
    isFlashSale: false,
    name: "ALOPE 4K Monitor",
  },
  {
    dataFilter: "workbench",
    img: "/src/assets/product/workbench/1.webp",
    isDiscount: false,
    isPopular: false,
    isNew: false,
    hasColors: false,
    isFlashSale: false,
    name: "ALOPE Alien Ware",
  },
];
</script>
<template>
  <Navbar :language="language" />

  <!--  -->

  <main
    class="container mx-auto lg:px-20 md:px-10 px-3 grid grid-cols-4 mt-10 gap-5 dark:text-gray-200"
  >
    <div class="md:flex justify-between col-span-4">
      <div>
        <h6>
          Hasil pencarian
          <span class="font-semibold inline-block mr-2"
            >"Produk Murah Meriah"</span
          >
          <span class="text-gray-400">(10 Produk)</span>
        </h6>
      </div>
      <div class="flex gap-6 md:mt-0 mt-5">
        <Button outline gradient="purple-blue">
          <span class="flex">
            <FilterIcon myClass="w-5 mr-1" />
            Filter
          </span>
          <template #suffix>
            <ChevronDownIcon myClass="w-3" />
          </template>
        </Button>
        <Button outline gradient="purple-blue">
          <span class="flex">
            <SortByIcon myClass="w-5 mr-1" />
            Urutkan
          </span>
          <template #suffix>
            <ChevronDownIcon myClass="w-3" />
          </template>
        </Button>
      </div>
    </div>

    <section
      class="grid lg:grid-cols-4 md:grid-cols-2 col-span-4 md:gap-5 gap-2"
    >
      <ProductCard
        v-for="product in products"
        :key="product"
        :img="product.img"
        :isDiscount="product.isDiscount"
        :isPopular="product.isPopular"
        :isNew="product.isNew"
        :hasColors="product.hasColors"
        :isFlashSale="product.isFlashSale"
        :language="language"
        :name="product.name"
      />
    </section>
  </main>

  <!--  -->

  <Footer :language="language" />
</template>

<script>
export default {
  data() {
    return {
      language: "id",
    };
  },
};
</script>

<style>
</style>