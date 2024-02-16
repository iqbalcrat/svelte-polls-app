

<script>
    import Button from "../shared/Button.svelte";
    let fields = {question: '', answerA: '', answerB: ''}
    let errors = {question: '', answerA: '', answerB: ''}
    let valid = false;

    const submitHandler = () =>{
        valid = true;
        if (fields.question.trim().length < 5) {
            valid = false;
            errors.question = "Questin should be at least 5 chars long"
        }
        else{
            errors.question = "";
        }


        //answer a

        if (fields.answerA.trim().length < 1) {
            valid = false;
            errors.answerA = "Answer should be at least 1 chars long"
        }
        else{
            errors.answerA = "";
        }


        //answer b

        if (fields.answerB.trim().length < 1) {
            valid = false;
            errors.answerB = "Answer should be at least 1 chars long"
        }
        else{
            errors.answerB = "";
        }

    }
</script>


<form on:submit|preventDefault={submitHandler} >
    <div class="form-field">
        <label for="question">Poll question:</label>
        <input type="text" id="question" bind:value={fields.question}>
    </div>

    <div class="form-field">
        <label for="answer-a">Answer A:</label>
        <input type="text" id="answer-a" bind:value={fields.answerA}>
    </div>

    <div class="form-field">
        <label for="answer-b">Answer B:</label>
        <input type="text" id="answer-b" bind:value={fields.answerB}>
    </div>
    <Button type="primary"> Add Poll</Button>
</form>



<style>

    form{
        width: 400px;
        margin: 0 auto;
        text-align: center;
    }

    .form-field{
        margin: 18px auto;
    }

    input{
        width: 100%;
        border-radius: 6px;
    }

    label{
        margin: 10px auto;
        text-align: left;
    }
</style>