<template>
<div id="app" class="container-fluid">
        <div class="row">
            <div class="menu-topo">
                <div class="alinhaPagina">
                    <ul>
                        <li class="no-mobile"><a href="https://www.reachr.com.br/#/Vagas" target="_blank">Vagas Recentes</a><span>|</span></li>
                        <li class="no-mobile"><a href="https://www.reachr.com.br/#/empresa" target="_blank">Cadastrar Empresa</a><span>|</span></li>
                        <li class="no-mobile"><a href="https://www.reachr.com.br/#/candidato" target="_blank">Candidato</a><span>|</span></li>
                        <li class="no-mobile"><a href="#faleconosco">Fale Conosco</a></li>
                        <li class="no-mobile"><a href="https://www.reachr.com.br/#/Home" target="_blank">Acesse sua Conta</a></li>
                    </ul>
                </div>
            </div>
        </div>
        <div class="row">
            <div class="qdo-destaque">
                <img class="img-destaque" src="./assets/img/foto-destaque.jpg" alt="" />
                <div class="qdo-inner">
                    <div class="alinhaPagina">
                        <div class="logo">
                            <img src="./assets/img/logo.png" alt="Bolsa-de-Empregos" />
                            <span></span>
                            <img src="./assets/img/logo-call.png" alt="Callcenter.inf" />
                        </div>
                        <div class="row">
                            <div class="cx-login">
                                <h2>faça seu login</h2>
                                    <div class="cx cx-empresa">
                                        <a href="https://www.reachr.com.br/#/empresa" target="_blank"><span class="be-btn be-btn-emp">sou empresa</span></a>
                                        <span>vagas disponíveis: {{ qtdVagas }}</span>
                                        <h3></h3>
                                    </div>
                                    <div class="cx cx-candidato">
                                        <a href="https://www.reachr.com.br/#/candidato" target="_blank"><span class="be-btn be-btn-can">sou candidato</span></a>
                                        <span>candidatos: {{ qtdCandidatos }}</span>
                                        <h3></h3>
                                    </div>
                                <div class="col-xs-offset-0 col-sm-4 col-md-8"></div>
                            </div>
                        </div>
                        <div class="divSeparador"></div>
                        <div class="divSeparador"></div>
                        <div class="row">
                            <div class="col-md-4" v-for="vaga in vagas.Itens">
                                <div class="cx-vagas cx-vagas-disponiveis">
                                    <div v-if="vaga.Empresa.Caracteristica != null && 
                                               vaga.Empresa.Caracteristica.Logo != ''">
                                        <img class="icn" :src="vaga.Empresa.Caracteristica.Logo" />
                                    </div>
                                    <div v-else>
                                        <img class="icn" src="./assets/img/sem-logo.png" />
                                    </div>
                                    <p class="tit">
                                        <span>{{vaga.Part.nome}}</span>
                                    </p>
                                    <div>
                                        {{vaga.Part.descricaoVaga.substring(0, 150)}}...
                                    </div>
                                    <button class="btnVaga" v-on:click="cadastrar(vaga.InternalId)">Quero me candidatar</button>
                                </div>
                            </div>
                        </div>
                   </div>
                </div>
            </div>
        </div>
        <div class="row">
            <div class="alinhaPagina">
                <div class="qdo qdo-emp-contratando">
                    <h2>Empresas Contratando pela Bolsa</h2>
                    <p><img src="./assets/img/emp-contratando.jpg" alt="Empresas-Contratando" /></p>
                </div>
            </div>
        </div>
        <div class="row">
            <div class="qdo qdo-carrinho">
                <p><img src="./assets/img/carrinho.png" alt="" /></p>
                <h1>
                    Aproveite agora e vamos customizar<br />
                    um plano exclusivo para você!
                </h1>
                <p><a href="https://www.reachr.com.br/#/demonstracao" target="_blank"><span class="btn">Solicite seu plano agora!</span></a></p>
            </div>
        </div>
        <div class="row">
            <div class="qdo qdo-blog">
                <div class="alinhaPagina">
                    <p class="tit"><a href="http://blogclientesa.clientesa.com.br" target="_blank"><span class="be-btn clsa-bg-color">Blog da Bolsa</span></a></p>
                    <div class="col-md-3">
                        <div class="cx-blog cx-vagas-disponiveis"></div>
                    </div>
                    <div class="col-md-3">
                        <div class="cx-blog cx-vagas-disponiveis"></div>
                    </div>
                    <div class="col-md-3">
                        <div class="cx-blog cx-vagas-disponiveis"></div>
                    </div>
                    <div class="col-md-3">
                        <div class="cx-blog cx-vagas-disponiveis"></div>
                    </div>
                </div>
            </div>
        </div>

        <div class="qdo qdo-anuncie">
            <div class="alinhaPagina">
                <div class="row">
                    <div class="col-md-6">
                        <h1>A bolsa do Callcenter.inf.br e da ClienteSA é uma parceria com a Reachr</h1>
                        <p><a href="https://www.reachr.com.br/#/Home" target="_blank"><span class="be-btn be-btn-emp">Anuncie as vagas da sua empresa agora!</span></a></p>
                    </div>
                    <div class="col-md-6">
                        <p>
                            Com tecnologia de ponta, própria e exclusiva, a Reachr indica os candidatos perfeitos para a posição.
                            Faz isto com simplicidade e rapidez porque entende a importância estratégica do recrutamento assertivo.
                        </p>
                        <p>
                            Para os profissionais de vendas e estagiários, a vaga oferecida é aquela que ele quer. Reachr oferece ferramentas para que
                            possam analisar o seu perfil e se tornar ainda mais atraente ao mercado.
                        </p>
                        <p class="ent-contato"><a href="#"><span>Ou entre em contato conosco</span></a></p>
                    </div>
                </div>
                <div class="qdo row">
                    <div class="col-md-4">
                        <p><img src="./assets/img/tools.png" alt="" /></p>
                        <p><a href="#"><span class="be-btn">Conheça nossos principais diferenciais</span></a></p>
                    </div>
                    <div class="col-md-4">
                        <p><img src="./assets/img/celular.png" alt="" /></p>
                        <p><a href="#"><span class="be-btn">Aplicativo para candidatos e empresas</span></a></p>
                    </div>
                    <div class="col-md-4">
                        <p><img src="./assets/img/grafico.png" alt="" /></p>
                        <p><a href="#"><span class="be-btn">Dicas e consultoria sobre carreira</span></a></p>
                    </div>
                </div>
            </div>
        </div>
        <div class="row">
            <div id="faleconosco" class="qdo fale-conosco">
                <div class="alinhaPagina">
                    <div class="col-md-6">
                        <h1>Fale Conosco!</h1>
                        <p>
                            A Plataforma está aqui para atender suas necessidades de carreira. Por isso, a REACHR está sempre disposta
                            a ouvir o que você tem a dizer.
                        </p>
                        <p>
                            Dúvidas, reclamações, críticas construtivas e elogios só fazem melhorar o desenvolvimento do
                            trabalho realizado. Você pode enviar um e-mail para nós ou utilizar o formulário de contato.
                        </p>

                    </div>
                    <div class="col-md-6">
                        <div class="qdo rodape">
                            <div class="col-md-6">
                                <p><input type="text" placeholder="Seu nome" id="txtNome" value="" /></p>
                                <p><input type="text" placeholder="telefone" id="txtTelefone" value="" /></p>
                            </div>
                            <div class="col-md-6">
                                <p><input type="text" placeholder="Seu e-mail" id="txtEmail" value="" /></p>
                                <p><input type="text" placeholder="Assunto" id="txtAssunto" value="" /></p>
                            </div>
                            <div class="col-md-12">
                                <p><textarea id="txtMensagem" placeholder="Mensagem"></textarea></p>
                                <p><span class="be-btn be-btn-emp">Enviar</span></p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <div class="row">
            <div class="rodape">
                <div class="col-md-4">
                    <p><img src="./assets/img/ic-ender.png"  alt="Endereço"/></p>
                    <p><span>Endereço:</span>
                    Rua do Rócio, 84 - Vila Olímpia - São Paulo / SP - Brasil</p>
                </div>
                <div class="col-md-4">
                    <p><img src="./assets/img/ic-tel.png" alt="Telefone" /></p>
                    <p><span>Telefone:</span>
                    +55(11) 3527-7802</p>
                </div>
                <div class="col-md-4">
                    <p><img src="./assets/img/ic-email.png" alt="E-mail" /></p>
                    <p><span>E-mail:</span>
                        <a href="mailto:atendimento@reachr.com.br">atendimento@reachr.com.br</a></p>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import axios from 'axios';
var serviceBase = 'https://www.reachr.com.br/';
export default {
    name: 'app',
    data () {
        return {
            qtdCandidatos : 0,
            qtdVagas: 0,
            vagas: [],
            cadastrar: function(id){
                window.open("https://www.reachr.com.br/#/Vaga/" + id, "_blank") ;
            }
        }
    },
    created(){

        this.$http.get(serviceBase + 'api/Engine/GetQuantidadeCadastro')
        .then(function(res){
            var data = res.data;

            this.qtdCandidatos = data.Candidatos;
            this.qtdVagas = data.Vagas;
        });

        //this.$http.get(serviceBase + 'api/VagaParts/MostrarNaHome/99')
        this.$http.get(serviceBase + 'api/VagaCandidatoParts/allclusters/3/1')
        .then(function(res){
            this.vagas = res.data;
        });

        axios.get("http://clientesa.com.br/data/jsonblogclientesa.ashx")
        .then(function(res){
            console.log(res);
        });
        
    }
}
</script>

<style>
.cx-vagas .btnVaga{
    background-color: white;
    border-radius: 30px;
    border-color: orange;
    padding: 10px 24px 11px;
    position: relative;
    top: 35px;
    left: 55px;
}
</style>
