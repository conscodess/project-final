<script>
    let { title, subtitle } = $props();
</script>

<div class="title-card">
    <div class="content">
        <h1>{title}</h1>
        <p>{subtitle}</p>
         <img class="seal-image" src="seal.png" alt="Nice gold seal for diploma" />
    </div>
      
    

</div>

<style>
    .title-card {
        background-color: #ffffff;
        height: 100vh;
        display: flex;
        justify-content: center;
        align-items: center;
        text-align: center;
        padding: 2rem;
        box-sizing: border-box;
       font-family: 'Garamond', serif;
       
    }

    .content {
        max-width: 700px;
        background-color: #ffffff;
        padding: 2rem;
        border: 6px solid #ffffff;
        border-radius: 2rem;
        text-align: center;
        

    }

    h1 {
        font-size: 3rem;
        margin: 0;
        color: #000000;
        text-shadow: 1px 1px 0 #847b11;
    }

    p {
        font-size: 1.3rem;
        color: #000000;
        margin-top: 1rem;
    }

     .seal-image {
    
    margin-top: 1rem;
    width: 200px;
    height: auto;
    display: inline-block;
  }
  

    @media (max-width: 600px) {
        h1 {
            font-size: 2.2rem;
        }

        p {
            font-size: 1.1rem;
        }
    }
</style>