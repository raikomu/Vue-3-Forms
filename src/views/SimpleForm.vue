<template>
  <div>
    <h1>Create an event</h1>
    <form>

      <BaseSelect
        v-model="event.category"
        :options="categories"
        label="Select a category"
      />

      <h3>Name & describe your event</h3>

      <BaseInput
        v-model="event.title"
        label="Title"
        type="text"
      />

      <BaseInput
        v-model="event.description"
        label="Description"
        type="text"
      />

      <h3>Where is your event?</h3>

      <BaseInput
        v-model="event.location"
        label="Location"
        type="text"
      />

      <h3>Are pets allowed?</h3>
      <div>
        <BaseRadio
          :value="1"
          name="pets"
          label="Yes"
          v-model="event.pets"
        />
      </div>

      <div>
      <div>
        <BaseRadio
          :value="0"
          name="pets"
          label="No"
          v-model="event.pets"
        />
      </div>
      </div>

      <h3>Extras</h3>
      <div>
        <input
          type="checkbox"
          v-model="event.extras.catering"
          class="field"
        />
        <label>Catering</label>
      </div>

      <div>
        <input
          type="checkbox"
          v-model="event.extras.music"
          class="field"
        />
        <label>Live music</label>
      </div>

      <button class="button -fill-gradient" type="submit">Submit</button>
    </form>
  </div>
</template>

<script>
export default {
  data () {
    return {
      categories: [
        'sustainability',
        'nature',
        'animal welfare',
        'housing',
        'education',
        'food',
        'community'
      ],
      event: {
        category: '',
        title: '',
        description: '',
        location: '',
        pets: 1,
        extras: {
          catering: false,
          music: false
        }
      }
    }
  }
}
</script>
