<script>
    let name;
    let location;
    let age;
    let mobile;
    let gender=[];
    const handleSubmit=() => {
        console.log(name,location,age,mobile,gender)
    }
</script>


<form on:submit preventDefault={handleSubmit}>
    <input type="text" placeholder="Name" bind:value={name}/>
    <input type="number" placeholder="age" bind:value={age}/>
    <input type="number" placeholder="mobile" bind:value={mobile}/>
    <label>Gender: </label>
    <input type="checkbox" bind:group={gender} value="Male"/>Male<br/>
    <input type="checkbox" bind:group={gender} value="Female"/>Female<br/>
    <label>Location</label>
    <select bind:value={location}>
        <option value="Chennai">Chennai</option>
        <option value="Bangalore">Bangalore</option>
        <option value="Nagercoil">Nagercoil</option>
    </select>
    <button>Add person</button>
</form>

<style>

</style>