<body>
  <main>
    <nav>
      <div class="nav-option selected" data-index="0">Overview</div>
      <div class="nav-option" data-index="1">Usuários</div>
      <div class="nav-option" data-index="2">Opções</div>
      <span class="shadow"></span>
    </nav>
    <div class="content">
      <div class="sections">
        <div class="option" data-index="0">
          <span>Conteúdo da opção "Overview".</spam>
        </div>
        <div class="option" data-index="1">
          <span>Conteúdo da opção "Usuários".</spam>
        </div>
        <div class="option" data-index="2">
          <span>Conteúdo da opção "Opções".</spam>
        </div>
      </div>
    </div>
  </main>
</body>

<div align="center">
  <a href="https://github.com/dwmartins">
  <img height="150px" src="https://github-readme-stats.vercel.app/api?username=conradosu&show_icons=true&theme=dark&include_all_commits=true&count_private=true"/>
</div>

<script>
document.querySelector('nav').addEventListener('click', (e) => {
  if (e.target.className.includes("nav-option")) {
    const index = parseInt(e.target.getAttribute('data-index'));
    
    document.querySelector('.sections').style.transform = `translateX(${index * -100}%)`;
    
    for (var i = 0; i < document.querySelectorAll('.nav-option').length; i++) {
      document.querySelectorAll('.nav-option')[i].classList.remove('selected');
    }
    e.target.classList.add('selected');
  }
});

document.querySelector('nav').addEventListener('mouseover', (e) => {
  if (e.target.className.includes("nav-option")) {
    document.querySelector('.shadow').style = `
      width:${e.target.offsetWidth}px;
      opacity:1;
      left:${e.target.offsetLeft}px;
     `;
  }
});

document.querySelector('nav').addEventListener('mouseout', () => {
  document.querySelector('.shadow').style.opacity = 0;
});  
</script>
  
<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;500&display=swap');

body {
  display:flex;
  justify-content:center;
  align-items:flex-start;
  padding:0;
  margin:0;
  font-family:'Roboto';
  background-color:black;
}
main {
  width:100%;
  max-width:750px;
  height:350px;
  padding:15px;
}
nav {
  width:100%;
  display:flex;
  justify-content:flex-start;
  align-items:center;
  position:relative;
  border-bottom:1px solid rgba(255,255,255,0.2);
  margin-bottom:15px;
}
.nav-option {
  padding:15px 12px 15px 10px;
  cursor:pointer;
  font-size:1rem;
  line-height:1rem;
  font-weight:300;
  color:white;
  opacity:0.5;
  position:relative;
  z-index:1;
  border-bottom:2px solid transparent;
  transition:ease 0.2s;
}
.selected {
  opacity:1;
  border-bottom:2px solid white;
}
.shadow {
  width:86px;
  height:70%;
  background-color:rgba(255,255,255,0.2);
  position:absolute;
  left:0;
  border-radius:3px;
  opacity:0;
  pointer-events:none;
  transition:ease-out 0.15s;
}
.content {
  width:100%;
  height:150px;
  background-color:rgba(255,255,255,0.1);
  border-radius:3px;
  overflow:hidden;
}
.sections {
  width:100%;
  height:100%;
  transform:translateX(0);
  display:flex;
  transition:ease 0.3s;
}
.option {
  min-width:100%;
  display:flex;
  justify-content:center;
  align-items:center;
}
.option > span {
  color:white;
}
</style>
