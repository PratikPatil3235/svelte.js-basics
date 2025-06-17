<script>
  const formValue = {
    name: "",
    profileSummery: "",
    country: "",
    jobLocation: [],
    remoteWork: false,
    skillSet: [],
    yearsOfExperience: "",
  };

  function submitForm() {
    console.log(formValue);
  }
</script>

<main>
  <form on:submit|preventDefault={submitForm}>
    <h2>🎨 Candidate Form</h2>

    <div class="form-group">
      <label for="name">Full Name</label>
      <input
        type="text"
        id="name"
        bind:value={formValue.name}
        placeholder="Enter your name"
      />
    </div>

    <div class="form-group">
      <label for="profile">Profile Summary</label>
      <textarea
        id="profile"
        bind:value={formValue.profileSummery}
        placeholder="Brief summary about yourself"
      ></textarea>
    </div>

    <div class="form-group">
      <label for="country">Country</label>
      <select id="country" bind:value={formValue.country}>
        <option value="">🌍 Select a Country</option>
        <option value="india">🇮🇳 India</option>
        <option value="vietnam">🇻🇳 Vietnam</option>
        <option value="singapore">🇸🇬 Singapore</option>
      </select>
    </div>

    <div class="form-group">
      <label for="job-location">Preferred Job Locations</label>
      <select id="job-location" bind:value={formValue.jobLocation} multiple>
        <option value="india">🇮🇳 India</option>
        <option value="vietnam">🇻🇳 Vietnam</option>
        <option value="singapore">🇸🇬 Singapore</option>
      </select>
    </div>

    <div class="form-group checkbox-group">
      <label class="checkbox-label">
        <input type="checkbox" bind:checked={formValue.remoteWork} />
        Open to Remote Work?
      </label>
    </div>

    <fieldset class="form-group checkbox-group">
      <legend>Skill Set</legend>
      <label
        ><input type="checkbox" value="html" bind:group={formValue.skillSet} /> HTML</label
      >
      <label
        ><input type="checkbox" value="css" bind:group={formValue.skillSet} /> CSS</label
      >
      <label
        ><input
          type="checkbox"
          value="javascript"
          bind:group={formValue.skillSet}
        /> JavaScript</label
      >
    </fieldset>

    <fieldset class="form-group radio-group">
      <legend>Years of Experience</legend>
      <label
        ><input
          type="radio"
          value="0-2"
          bind:group={formValue.yearsOfExperience}
        /> 0-2</label
      >
      <label
        ><input
          type="radio"
          value="3-5"
          bind:group={formValue.yearsOfExperience}
        /> 3-5</label
      >
      <label
        ><input
          type="radio"
          value="6-10"
          bind:group={formValue.yearsOfExperience}
        /> 6-10</label
      >
    </fieldset>

    <div class="form-group">
      <button type="submit">🚀 Submit</button>
    </div>
  </form>

  <div class="output">
    <h3>📋 Preview</h3>
    <pre>{JSON.stringify(formValue, null, 2)}</pre>
  </div>
</main>

<style>
  :root {
    --primary: #4e8cff;
    --accent: #ff6f91;
    --bg-light: #f0f4f8;
    --white: #ffffff;
    --text: #333;
    --shadow: rgba(0, 0, 0, 0.1);
  }

  main {
    background: var(--bg-light);
    padding: 2rem;
    max-width: 700px;
    margin: 2rem auto;
    border-radius: 16px;
    box-shadow: 0 8px 20px var(--shadow);
    font-family: "Segoe UI", sans-serif;
  }

  h2 {
    text-align: center;
    color: var(--accent);
    margin-bottom: 1.5rem;
  }

  .form-group {
    margin-bottom: 1.2rem;
    display: flex;
    flex-direction: column;
  }

  label,
  legend {
    font-weight: bold;
    color: var(--primary);
    margin-bottom: 0.5rem;
  }

  input,
  textarea,
  select {
    padding: 0.6rem 0.8rem;
    border: 2px solid var(--primary);
    border-radius: 8px;
    font-size: 1rem;
    transition: all 0.2s ease;
    background-color: var(--white);
  }

  input:focus,
  textarea:focus,
  select:focus {
    border-color: var(--accent);
    outline: none;
    box-shadow: 0 0 0 3px rgba(255, 111, 145, 0.3);
  }

  select[multiple] {
    height: 100px;
  }

  .checkbox-group label,
  .radio-group label {
    display: flex;
    align-items: center;
    gap: 0.5rem;
    margin-bottom: 0.5rem;
    font-weight: normal;
    color: var(--text);
  }

  fieldset {
    border: none;
    padding: 0;
  }

  button {
    padding: 0.7rem 1.5rem;
    font-size: 1rem;
    font-weight: bold;
    background-color: var(--primary);
    color: var(--white);
    border: none;
    border-radius: 8px;
    cursor: pointer;
    transition:
      background-color 0.2s ease,
      transform 0.1s ease;
  }

  button:hover {
    background-color: var(--accent);
    transform: translateY(-2px);
  }

  .output {
    margin-top: 2rem;
    background: var(--white);
    border-left: 6px solid var(--accent);
    padding: 1rem;
    border-radius: 12px;
    font-family: monospace;
    font-size: 0.95rem;
    color: var(--text);
    box-shadow: 0 4px 10px var(--shadow);
  }

  .output h3 {
    margin-bottom: 0.5rem;
    color: var(--primary);
  }
</style>
