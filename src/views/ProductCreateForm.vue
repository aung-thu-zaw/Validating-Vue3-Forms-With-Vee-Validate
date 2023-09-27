<template>
  <section class="bg-white dark:bg-gray-900">
    <div class="py-8 px-4 mx-auto max-w-2xl lg:py-16">
      <h2 class="mb-4 text-xl font-bold text-gray-900 dark:text-white">
        Add a new product
      </h2>
      <form @submit.prevent="submit">
        <div class="grid gap-4 sm:grid-cols-2 sm:gap-6">
          <div class="sm:col-span-2">
            <label
              for="name"
              class="block mb-2 text-sm font-medium text-gray-900 dark:text-white"
              >Product Name</label
            >
            <input
              type="text"
              name="name"
              id="name"
              class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-primary-600 focus:border-primary-600 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-primary-500 dark:focus:border-primary-500"
              placeholder="Type product name"
              v-model="name"
            />

            <span class="text-red-700 text-xs font-semibold">
              {{ errors?.name }}
            </span>
          </div>
          <div class="w-full">
            <label
              for="brand"
              class="block mb-2 text-sm font-medium text-gray-900 dark:text-white"
              >Brand</label
            >
            <input
              type="text"
              name="brand"
              id="brand"
              class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-primary-600 focus:border-primary-600 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-primary-500 dark:focus:border-primary-500"
              placeholder="Product brand"
              v-model="brand"
            />
            <span class="text-red-700 text-xs font-semibold">
              {{ errors?.brand }}
            </span>
          </div>
          <div class="w-full">
            <label
              for="price"
              class="block mb-2 text-sm font-medium text-gray-900 dark:text-white"
              >Price</label
            >
            <input
              type="number"
              name="price"
              id="price"
              class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-primary-600 focus:border-primary-600 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-primary-500 dark:focus:border-primary-500"
              placeholder="$2999"
              v-model="price"
            />
            <span class="text-red-700 text-xs font-semibold">
              {{ errors?.price }}
            </span>
          </div>
          <div>
            <label
              for="category"
              class="block mb-2 text-sm font-medium text-gray-900 dark:text-white"
              >Category</label
            >
            <select
              id="category"
              class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-primary-500 focus:border-primary-500 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-primary-500 dark:focus:border-primary-500"
              v-model="category"
            >
              <option selected="">Select category</option>
              <option value="TV">TV/Monitors</option>
              <option value="PC">PC</option>
              <option value="GA">Gaming/Console</option>
              <option value="PH">Phones</option>
            </select>
            <span class="text-red-700 text-xs font-semibold">
              {{ errors?.category }}
            </span>
          </div>
          <div>
            <label
              for="item-weight"
              class="block mb-2 text-sm font-medium text-gray-900 dark:text-white"
              >Item Weight (kg)</label
            >
            <input
              type="number"
              name="item-weight"
              id="item-weight"
              class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-primary-600 focus:border-primary-600 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-primary-500 dark:focus:border-primary-500"
              placeholder="12"
              v-model="weight"
            />
            <span class="text-red-700 text-xs font-semibold">
              {{ errors?.weight }}
            </span>
          </div>

          <div class="flex items-center space-x-5">
            <div class="flex items-center">
              <input
                id="checked-checkbox"
                type="checkbox"
                value=""
                class="w-4 h-4 text-blue-600 bg-gray-100 border-gray-300 rounded focus:ring-blue-500 dark:focus:ring-blue-600 dark:ring-offset-gray-800 focus:ring-2 dark:bg-gray-700 dark:border-gray-600"
                v-model="featured"
              />
              <label
                for="checked-checkbox"
                class="ml-2 text-sm font-medium text-gray-900 dark:text-gray-300"
              >
                Featured
              </label>
            </div>
            <div class="flex items-center">
              <input
                id="checked-checkbox"
                type="checkbox"
                value=""
                class="w-4 h-4 text-blue-600 bg-gray-100 border-gray-300 rounded focus:ring-blue-500 dark:focus:ring-blue-600 dark:ring-offset-gray-800 focus:ring-2 dark:bg-gray-700 dark:border-gray-600"
                v-model="special"
              />

              <label
                for="checked-checkbox"
                class="ml-2 text-sm font-medium text-gray-900 dark:text-gray-300"
              >
                Special Offer
              </label>
            </div>
          </div>

          <div class="flex items-center space-x-5">
            <div class="flex items-center">
              <input
                id="default-radio-1"
                type="radio"
                value=""
                name="default-radio"
                class="w-4 h-4 text-blue-600 bg-gray-100 border-gray-300 focus:ring-blue-500 dark:focus:ring-blue-600 dark:ring-offset-gray-800 focus:ring-2 dark:bg-gray-700 dark:border-gray-600"
                v-model="warranty"
              />
              <label
                for="default-radio-1"
                class="ml-2 text-sm font-medium text-gray-900 dark:text-gray-300"
                >No warranty</label
              >
            </div>
            <div class="flex items-center">
              <input
                checked
                id="default-radio-2"
                type="radio"
                value=""
                name="default-radio"
                class="w-4 h-4 text-blue-600 bg-gray-100 border-gray-300 focus:ring-blue-500 dark:focus:ring-blue-600 dark:ring-offset-gray-800 focus:ring-2 dark:bg-gray-700 dark:border-gray-600"
                v-model="warranty"
              />

              <label
                for="default-radio-2"
                class="ml-2 text-sm font-medium text-gray-900 dark:text-gray-300"
                >14 days warranty</label
              >
            </div>
          </div>
          <div class="sm:col-span-2">
            <label
              for="description"
              class="block mb-2 text-sm font-medium text-gray-900 dark:text-white"
              >Description</label
            >
            <textarea
              id="description"
              rows="8"
              class="block p-2.5 w-full text-sm text-gray-900 bg-gray-50 rounded-lg border border-gray-300 focus:ring-primary-500 focus:border-primary-500 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-primary-500 dark:focus:border-primary-500"
              placeholder="Your description here"
              v-model="description"
            ></textarea>
            <span class="text-red-700 text-xs font-semibold">
              {{ errors?.description }}
            </span>
          </div>
        </div>
        <button
          type="submit"
          class="inline-flex items-center px-5 py-2.5 mt-4 sm:mt-6 text-sm font-medium text-center text-white bg-blue-700 rounded-lg focus:ring-4 focus:ring-blue-200 dark:focus:ring-blue-900 hover:bg-blue-800"
        >
          Add product
        </button>
      </form>
    </div>
  </section>
</template>

<script>
import { useForm, useField } from "vee-validate";
export default {
  setup() {
    // Validation Rules
    const required = (value) => {
      const requiredMessage = "This field is required";
      if (!value) return requiredMessage;

      if (value === undefined || value === null) return requiredMessage;

      if (!String(value).length) return requiredMessage;

      return true;
    };

    const minLength = (number, value) => {
      if (String(value).length < number)
        return `Please type at least ${number} characters`;

      return true;
    };

    const anything = () => {
      return true;
    };

    const validationSchema = {
      name: (value) => {
        const req = required(value);
        if (req !== true) return req;

        const min = minLength(5, value);
        if (min !== true) return min;

        return true;
      },
      price: required,
      category: required,
      description: required,
      weight: undefined,
      brand: undefined,
      special: anything,
      featured: anything,
      warranty: anything,
    };

    const { handleSubmit, errors } = useForm({
      validationSchema,
      initialValues: {
        featured: false,
        special: false,
        warranty: 0,
      },
    });

    const { value: name } = useField("name");
    const { value: brand } = useField("brand");
    const { value: price } = useField("price");
    const { value: category } = useField("category");
    const { value: weight } = useField("weight");
    const { value: description } = useField("description");
    const { value: featured } = useField("featured");
    const { value: special } = useField("special");
    const { value: warranty } = useField("warranty");

    const submit = handleSubmit((values) =>
      console.log("form is submitted.", values)
    );

    return {
      name,
      brand,
      price,
      category,
      weight,
      description,
      featured,
      special,
      warranty,
      errors,
      submit,
    };
  },
};
</script>

<style>
</style>