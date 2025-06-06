<template>
<div class="icon-row">
          <a href="https://www.linkedin.com/">
            <i class="fa-brands fa-linkedin linkdin" ></i>  
          </a>
          <a href="http://github.com/arya00ffff/">
            <i class="fa-brands fa-github github"></i>
          </a>
          <a href="mailto:arya@gmail.com">
            <i class="fa-regular fa-envelope email" ></i> 
          </a>
          <i class="fa-brands fa-telegram telegram"></i>
        </div>
</template>
<style scoped >
.icon-row {
  display: flex;
  gap: 16px; 
  align-items: center;
  font-size: 40px;
  cursor: pointer;
}

.linkdin {
  color: #bae6fd;
}
.linkdin:hover {
  color: #0072B1;
}
.light-mode .linkdin{
  color: #0385c7;
}
.light-mode .linkdin:hover{
  color:#065885;
}
.github {
color: #f0f6fc;
}
.github:hover {
  color: #333;
}
.light-mode .github{
  color: black;
}
.light-mode .github:hover{
  color: #333;
}
.email{
  color: #de5143;
}
.email:hover{
  color:#b04336;
}
.telegram{
  color:#24b3de;
}
.telegram:hover{
  color:#24A1DE;
}
</style>
