---
title: "Audioconferência no Microsoft Teams"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Orientações práticas para a implantação de Audioconferência no Microsoft Teams."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 5442f5bf11540f5429566bc683afaeb3a24ff4ac
ms.sourcegitcommit: 2592b268977460d0d483a75d741b1ce9fa8da908
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/28/2017
---
<a name="audio-conferencing-in-microsoft-teams"></a>Audioconferência no Microsoft Teams
=====================================

> [!IMPORTANT]
> A Audioconferência está em uma prévia pública. Está disponível para adotantes precoces (EA) e clientes da prévia, e poderá sofrer modificações ao ser lançada ou atualizada.

A Audioconferência do Office 365 (conhecida anteriormente como Conferência PSTN) permite que os participantes entrem em reuniões a partir de qualquer telefone. Esse recurso está agora disponível no Microsoft Teams em prévia pública, permitindo que os usuários entrem em reuniões do Teams usando seus telefones. As orientações práticas deste artigo levam você pela estrutura da jornada do cliente do Office 365 FastTrack para Audioconferência - Concepção, Integração e Geração de valor.

Eis o que você obtém com a [Audioconferência](https://go.microsoft.com/fwlink/?linkid=858992) no Office 365.

> [!NOTE]
> A Audioconferência suporta tanto o Teams, quanto o Skype for Business Online. No momento, o centro de administração do Skype for Business e o PowerShell remota oferecem as interfaces administrativas para gerenciar a Audioconferência.


|  |  |
|---------|---------|
|  <iframe width="350" height="200" src="https://www.youtube.com/embed/AGPvaW4Vg0o" frameborder="0" allowfullscreen></iframe>   | |

Concepção <a name="Envision_AudioConferencing"> </a>
=========

A fase de Concepção oferece a base a jornada do cliente Office 365 e se aplica a todas as cargas de trabalho, como a Audioconferência.

Nessa fase, os objetivos de negócios são estabelecidos com as partes envolvidas relevantes do projeto reunidas, para entregar:

-   um plano de sucesso e de alto nível que tenha casos de uso comercial, as principais partes envolvidas, os objetivos e os resultados principais(OKRs), os principais indicadores de sucesso (KSIs), os riscos, a avaliação do ambiente, a prontidão para adoção e o plano operacional.

-   e, posteriormente, um plano detalhado da implementação técnica da Audioconferência para atingir o status final desejado.

<a name="define-business-use-cases-for-audio-conferencing"></a>Definição de casos de uso comercial para Audioconferência
------------------------------------------------

A Audioconferência oferece à organização pontos de entradas adicionais para todas as reuniões agendadas ao permitir que os participantes entrem via PSTN discando pelo tradicional telefone fixo, PBX ou telefones celulares.

Isso é útil quando o organizador ou os participantes não estão na frente do computador ou quando as conexões de dados estão indisponíveis ou não são confiáveis para o suporte a comunicações de voz, como em áreas remotas com cobertura irregular de dados móveis ou conexão a um serviço de Wi-Fi público com largura de banda limitada, ou quando os participantes da reunião preferem discar para a reunião usando o endpoint de telefonia que possam acessar prontamente.

Nessa etapa, as principais partes envolvidas no projeto definirão os casos de uso comercial que suportem a implementação de Audioconferência.

Os casos de uso comercial devem definir e documentar os resultados comerciais esperados e mensuráveis, e incluir o que segue:

-   Descrição do processo comercial atual.

-   Definição dos desafios com os processos comerciais existentes.

-   Como a tecnologia pode ajudar a superar esses desafios.

-   Os resultados comerciais esperados e mensuráveis se esses desafios forem superados.

<table>
<tbody>
<tr class="header">
<th align="left"><p><img src="media/audio_conferencing_image2.png" /></p></th>
<td align="left"><p><strong>Descrição do processo comercial atual</strong></p>
<p>A Contoso conta atualmente com serviços de conferência PSTN fornecidos pelo provedor de telefonia local vigente, cobrados por minutos de reunião para reuniões internas e reuniões envolvendo partes externas.</p></td>
</tr>
<tr class="odd">
<td align="left"><p><img src="media/audio_conferencing_image3.png" /></p></td>
<td align="left"><p><strong>Desafios com os processos comerciais existentes</strong></p>
<p>A Contoso gasta cerca de US$ 1 milhão por ano com o serviço de conferência PSTN atual, com 75% do custo incorrendo para reuniões internas.</p>
<p>O uso dos endpoints tradicionais de telefonia para entrar em reuniões hospedadas pelo serviço de conferência PSTN não está alinhado com o plano de a organização adotar o Teams como uma plataforma de colaboração e comunicação moderna.</p></td>
</tr>
<tr class="even">
<td align="left"><p><img src="media/audio_conferencing_image4.png" /></p></td>
<td align="left"><p><strong>Como a tecnologia pode superar esses desafios</strong></p>
<p>Com a adoção do Microsoft Teams como uma plataforma de colaboração e comunicação moderna, espera-se que os usuários internos participem principalmente de reuniões usando seus PCs equipados com fones de ouvido otimizados e dispositivos de sala de reunião. O serviço de Audioconferência estará disponível para ter suporte para participantes externos ou situações em que o uso do áudio do PC não seja favorável para os participantes internos.</p></td>
</tr>
<tr class="odd">
<td align="left"><p><img src="media/audio_conferencing_image5.png" /></p></td>
<td align="left"><p><strong>Resultados comerciais esperados e mensuráveis</strong></p>
<p>A mudança para o Teams como uma plataforma de colaboração e comunicação moderna, aliada ao serviço de Audioconferência, reduzirá consideravelmente o custo de entrega do serviço de conferência PSTN, ao ponto que a Contoso deverá gastar apenas cerca de 20% do custo anual do serviço de conferência PSTN existente.</p></td>
</tr>
</tbody>
</table>

_Tabela 1 Exemplo de casos de uso comercial_


Além de definir os casos de uso comercial, ter clareza sobre o escopo organizacional e os cronogramas do projeto nessa fase ajudará na passagem para a próxima fase de Concepção.

<a name="identify-key-stakeholders"></a>Identificar as principais partes envolvidas
-------------------------

Os casos de uso comercial definidos na etapa anterior incluirão o escopo organizacional da implementação da Audioconferência e, com base nisso, a matriz abrangente das partes envolvidas pode ser completada para incluir as pessoas certas a serem envolvidas no projeto.

<table>
<thead>
<tr class="header">
<th align="left">Função</th>
<th align="left">Descrição</th>
<th align="left">Nome, informações de contato, localização</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><strong>Patrocinador executivo do projeto</strong></td>
<td align="left"><ul><li>A autoridade e a responsabilidade final pelo projeto e pela entrega dos objetivos do projeto</li>
<li>Ajudar a solucionar problemas escalados pelo Líder do projeto</li>
<li>Comunicação do patrocinador internamente na empresa sobre os objetivos do projeto</li>
<li>Responsável pela tomada de decisões estratégicas</li>
<li>Responsável pela disponibilidade do orçamento e dos recursos necessários</p>
<li>Liderança da avaliação trimestral de negócios (QBR)</li>
<li>Aceitação e ajuda nos esforços da campanha de conscientização</li>
<li>Atuando como patrocinador do projeto de distribuição do programa</li></ul></td>
<td align="left">TBA</td>
</tr>
<tr class="even">
<td align="left"><strong>Líder de projeto</strong></td>
<td align="left"><ul><li>Gerenciamento e liderança da equipe do projeto</li>
<li>Coordena os parceiros e as equipes de trabalho envolvidos no projeto</li>
<li>Responsável pela criação e pelo gerenciamento dos planos do projeto para atingir os principais resultados trimestrais</li>
<li>Solucionar problemas multifuncionais</li>
<li>Passar atualizações regulares aos patrocinadores do projeto</li>
<li>Incorporação dos aspectos de adoção em todo o plano do projeto</li>
<li>Liderança das avaliações mensais de negócios e operações (MBR), contribuindo com as avaliações trimestrais de negócios</li></ul></td>
<td align="left">TBA</td>
</tr>
<tr class="odd">
<td align="left"><strong>Líder/arquiteto de colaboração</strong></td>
<td align="left"><ul><li>Responsável pela execução da estratégia de colaboração definida pelos executivos da empresa</li>
<li>Analisar e escolher produtos de colaboração para a empresa que atendam aos objetivos de negócios</li>
<li>Responsável pela concepção das operações dos produtos de colaboração</li>
<li>Define o modelo de operação e suporte</li>
<li>Contribuir com as avaliações trimestrais de negócios</li><ul></td>
<td align="left">TBA</td>
</tr>
<tr class="even">
<td align="left"><strong>Consultor</strong></td>
<td align="left"><ul><li>Responsável pelos serviços de configuração</li>
<li>Contribui na arquitetura geral da solução</li></ul></td>
<td align="left">TBA</td>
</tr>
<tr class="odd">
<td align="left"><strong>Gerente de projetos</strong></td>
<td align="left"><ul><li>Desenvolvimento e manutenção do plano do projeto</li>
<li>Gerenciar os produtos finais do projeto de acordo com o plano do projeto e o orçamento</li>
<li>Registrar e gerenciar os problemas de projeto, incluindo o dimensionamento</li>
<li>Conduzir chamadas stand up semanais</li>
<li>Conectar-se e passar atualizações para patrocinadores executivos do projeto</li>
<li>Trabalhar com o Arquiteto para definir a abordagem de gerenciamento de mudanças e os planos de comunicação</li></ul></td>
<td align="left">TBA</td>
</tr>
<tr class="even">
<td align="left"><strong>Gerenciamento de mudanças/Especialista em adoção</strong></td>
<td align="left"><ul><li>Alimentar a fase de Descoberta em processos de treinamento e adoção</li>
<li>Participar do workshop de estratégia de adoção</li>
<li>Desenvolvimento e responsabilidade pela estratégia de adoção</li>
<li>Desenvolvimento e execução do plano de comunicação</li>
<li>Responsável por ministrar treinamentos aos usuários finais</li>
<li>Coletar feedback e conduzir pesquisas</li></ul></td>
<td align="left">TBA</td>
</tr>
<tr class="odd">
<td align="left"><strong>Líder de rede</strong></td>
<td align="left"><ul><li>Alimentar a fase de Descoberta em design de rede</li>
<li>Participar do planejamento durante o workshop de Concepção</li>
<li>Coordena o trabalho da equipe de rede durante a execução do projeto</li></ul></td>
<td align="left">TBA</td>
</tr>
<tr class="even">
<td align="left"><strong>Líder de segurança</strong></td>
<td align="left"><ul><li>Alimentar a fase de Descoberta em processos e designs de segurança</li>
<li>Participar do planejamento durante o workshop de Concepção</li>
<li>Coordena o trabalho da equipe de segurança durante a execução do projeto</li></ul></td>
<td align="left">TBA</td>
</tr>
<tr class="odd">
<td align="left"><strong>Líder de telefonia</strong></td>
<td align="left"><ul><li>Alimentar a fase de Descoberta em design de telefonia</li>
<li>Participar do planejamento durante o workshop de Concepção</li>
<li>Coordena o trabalho da equipe de telefonia durante a execução do projeto</li></ul></td>
<td align="left">TBA</td>
</tr>
<tr class="even">
<td align="left"><strong>Líder de desktop</strong></td>
<td align="left"><ul><li>Alimentar a fase de Descoberta em clientes e processos de atualização</li>
<li>Participar do planejamento durante o workshop de Concepção</li>
<li>Coordena o trabalho da equipe de desktop durante a execução do projeto</li></ul></td>
<td align="left">TBA</td>
</tr>
<tr class="odd">
<td align="left"><strong>Líder de suporte/central de ajuda</strong></td>
<td align="left"><ul><li>Alimentar a fase de Descoberta em modelos de operação e suporte</li>
<li>Participar do planejamento durante o workshop de Concepção</li>
<li>Participar no planejamento do modelo de suporte</li>
<li>Coordena o trabalho das equipes/recursos de suporte durante a execução do projeto</li></ul></td>
<td align="left">TBA</td>
</tr>
<tr class="even">
<td align="left"><strong>Representantes das unidades de negócios</strong></td>
<td align="left"><ul><li>Contribuir com guias e materiais de adoção baseados no usuário final</li>
<li>Contribuir e analisar casos de uso comercial</li></ul></td>
<td align="left">TBA</td>
</tr>
<tr class="odd">
<td align="left"><strong>Líder de implantação</strong></td>
<td align="left"><ul><li>Garantir que os pré-requisitos de implantação sejam atendidos</li>
<li>Envolver os recursos do cliente para as atividades da fase de preparação e implantação</li>
<li>Participar de reuniões para analisar o status de preparação e implantação</li></ul></td>
<td align="left">TBA</td>
</tr>
<tr class="even">
<td align="left"><strong>Administradores de TI</strong></td>
<td align="left"><ul><li>Profissionais de TI responsáveis pela assistência no planejamento e execução de testes</li></ul></td>
<td align="left">TBA</td>
</tr>
<tr class="odd">
<td align="left"><strong>Proprietário do serviço</strong></td>
<td align="left"><ul><li>Responsável pela operação do serviço de Audioconferência</li>
<li>Proprietário do serviço de Audioconferência</li></ul></td>
<td align="left">TBA</td>
</tr>
<tr class="even">
<td align="left"><strong>Defensor da qualidade</strong></td>
<td align="left"><ul><li>Direciona qualidade, confiabilidade e feedback dos usuários</li>
<li>Identifica as tendências de qualidade e direciona remediação com as respectivas equipes</li>
<li>Reporta-se ao comitê de direção e de volta à liderança</li>
<li>Reporta-se sobre qualidade, confiabilidade e sentimento dos usuários através do Rate My Call e Net Promoter Score</li></ul></td>
<td align="left">TBA</td>
</tr>
</tbody>
</table>

_Tabela 2 Exemplo de modelo de matriz das partes envolvidas_


> [!NOTE]
> A tabela de exemplo acima e as tabelas subsequentes ao longo deste documento servem como modelo. Você verá “TBA” (a ser adicionado) para informações que você precisa inserir como parte do seu processo de planejamento.



<a name="define-objectives-and-key-results-key-success-indicators-and-risks"></a>Defina os objetivos e os resultados principais, os principais indicadores de sucesso e os riscos
--------------------------------------------------------------------

Com as partes envolvidas do projeto reunidas, os casos de uso comercial, o escopo organizacional e os cronogramas do projeto podem ser traduzidos em objetivos e resultados principais (OKRs), e as medições de sucesso do projeto podem ser definidas em uma lista de principais indicadores de sucesso (KSIs).

A participação das partes envolvidas do projeto na definição dos OKRs e KSIs assegurará o senso de propriedade e eles serão alinhados aos requisitos comerciais das empresas.

Os OKRs contêm a lista dos objetivos estabelecidos no início do projeto, com os principais resultados mensuráveis definidos em uma base trimestral. Os principais resultados são avaliados mensalmente para monitorar o status geral do projeto e, com base no progresso, podem ser feitos ajustes nos planos trimestrais conforme a necessidade.

<table>
<thead>
<tr class="header">
<th align="left"><p><strong>Visão</strong>: Aumentar a produtividade maximizando os investimentos no Office 365</p>
</th>
<th align="left"></th>
<th align="left"></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><strong>Objetivos</strong></td>
<td align="left"><strong>Resultados principais</strong></td>
<td align="left"><strong>A fazer</strong></td>
</tr>
<tr class="even">
<td align="left">Implantar Audioconferência no Teams até o final do ano fiscal de 2018</td>
<td align="left">1º trimestre do ano fiscal de 2018: Implantar Audioconferência no Teams globalmente</td>
<td align="left"><p>Concepção</p>
<ul><li>Criar plano de sucesso</li>
<li>Criar plano detalhado de implementação técnica</li></ul>
<p>Integração</p>
<ul><li>Executar plano de sucesso</li>
<li>Executar plano de implementação técnica</li></ul></td>
</tr>
<tr class="odd">
<td align="left">Encerrar globalmente o serviço de conferência PSTN herdado até o meio do ano fiscal de 2018</td>
<td align="left">2º trimestre do ano fiscal de 2018: Encerrar globalmente o serviço de conferência PSTN herdado</td>
<td align="left"><p>Gerar valor</p>
<ul><li>Aumentar o envolvimento do usuário e direcionar adoção</li>
<li>Gerenciar e preparar a mudança</li>
<li>Mensurar, compartilhar o sucesso e iterar</li></ul></td>
</tr>
</tbody>
</table>

_Tabela 3 Exemplo de OKRs_


Os KSIs mensuram a qualidade e o sucesso dos principais resultados e complementam a natureza binária dos OKRs (alcançados ou não alcançados) ao detalhar os bons e/ou maus resultados. Ao definir os KSIs, recomendamos aproveitar os critérios “específicos, mensuráveis, atribuíveis, realistas, relacionados ao tempo” ou SMART.

<table>
<thead>
<tr class="header">
<th align="left">Tipo</th>
<th align="left"><p>Perguntas de KSI &amp;</p>
<p>critérios</p></th>
<th align="left">Como foi mensurado</th>
<th align="left">Critérios de sucesso</th>
<th align="left">Mensurado</th>
<th align="left">Responsável</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><strong>Uso/adoção</strong></td>
<td align="left">A qualidade da chamada é igual ou melhor que a solução anterior</td>
<td align="left">Pesquisa</td>
<td align="left">80% dos usuários concordam ou concordam fortemente</td>
<td align="left">Após a habilitação e trimestralmente</td>
<td align="left">Esquipe de Tecnologia da Informação</td>
</tr>
<tr class="even">
<td align="left"><strong>Uso/adoção</strong></td>
<td align="left">O Teams facilitou o processo de comunicação</td>
<td align="left">Pesquisa</td>
<td align="left">80% dos usuários concordam ou concordam fortemente</td>
<td align="left">Após a habilitação e trimestralmente</td>
<td align="left">Equipe de gerenciamento de mudanças</td>
</tr>
<tr class="odd">
<td align="left"><strong>Uso/adoção</strong></td>
<td align="left">Os usuários usam a solução ativamente</td>
<td align="left">Relatórios do Office 365, Painel de Qualidade da Chamada</td>
<td align="left">80% dos usuários são usuários ativos diariamente</td>
<td align="left">Diariamente</td>
<td align="left">Equipe de gerenciamento de mudanças</td>
</tr>
<tr class="even">
<td align="left"><strong>Uso/qualidade</strong></td>
<td align="left">A porcentagem de chamadas/conferências de má qualidade deve ser mínima</td>
<td align="left">Painel de Qualidade da Chamada</td>
<td align="left">&lt; 5% de chamadas de má qualidade por mês</td>
<td align="left">Diariamente</td>
<td align="left">Esquipe de Tecnologia da Informação</td>
</tr>
<tr class="odd">
<td align="left"><strong>Uso/suporte</strong></td>
<td align="left">Eu sei como obter suporte técnico</td>
<td align="left">Pesquisa</td>
<td align="left">90% dos usuários concordam ou concordam fortemente</td>
<td align="left">Após a habilitação e trimestralmente</td>
<td align="left">Equipe de gerenciamento de mudanças</td>
</tr>
<tr class="even">
<td align="left"><strong>Uso/suporte</strong></td>
<td align="left">Estou satisfeito com a qualidade do suporte técnico</td>
<td align="left">Pesquisa</td>
<td align="left">80% dos usuários concordam ou concordam fortemente</td>
<td align="left">Após cada incidente</td>
<td align="left">Esquipe de Tecnologia da Informação</td>
</tr>
<tr class="odd">
<td align="left"><strong>Financeiro</strong></td>
<td align="left">Redução dos minutos de conferência herdados</td>
<td align="left">Sistema financeiro</td>
<td align="left">Atingir o ROI estabelecido</td>
<td align="left">Baseado no ROI</td>
<td align="left">Equipe de gerenciamento de mudanças</td>
</tr>
</tbody>
</table>

_Tabela 4 Exemplo de KSIs_


Como parte desse exercício, você precisa identificar os riscos de negócios e definir um plano de mitigação para cada um dos riscos identificados. Essas informações podem ser coletadas em um plano de riscos.

<table>
<thead>
<tr class="header">
<th align="left">Risco</th>
<th align="left">Probabilidade</th>
<th align="left">Impacto</th>
<th align="left">Geral</th>
<th align="left">Plano de mitigação</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">A incorporação acrescentará até 1.000 pessoas</td>
<td align="left">Alto</td>
<td align="left">Alto</td>
<td align="left">Alto</td>
<td align="left"><p>Para empresas incorporadas, separar o OKR com o processo próprio (Concepção, Integração, Geração de valor)</p>
<p>Não inclui-los nos OKRs existentes</p></td>
</tr>
<tr class="even">
<td align="left">A portabilidade dos números de telefone atrasará a conclusão do projeto</td>
<td align="left">Alto</td>
<td align="left">Alto</td>
<td align="left">Alto</td>
<td align="left"><p>Preparar todas as informações necessárias para dar suporte à portabilidade dos números de telefone antes (ou seja, registros do atendimento ao cliente, detalhes de cobrança, Carta de Autorização)</p>
<p>Ajustar o cronograma do projeto para absorver o tempo de entrega dos resultados da execução da portabilidade dos números de telefone</p>
<p>Comunicar o uso de novos números de conferência de discagem para os participantes externos</p></td>
</tr>
<tr class="odd">
<td align="left">Reestruturação planejada da rede</td>
<td align="left">Alto</td>
<td align="left">Médio</td>
<td align="left">Médio</td>
<td align="left">Antes de implementar o Teams como uma plataforma de colaboração e comunicação moderna, execute a avaliação da prontidão da rede para sites no âmbito do projeto</td>
</tr>
</tbody>
</table>

_Tabela 5 Exemplo de plano de risco_


<a name="assess-environment-and-evaluate-adoption-readiness"></a>Avalie o ambiente e avalie a prontidão para adoção
--------------------------------------------------

Para alcançar os OKRs pretendidos, você pode precisar definir a arquitetura de alto nível da solução. É necessária uma pesquisa do ambiente para avaliar todos os aspectos relacionados à infraestrutura de TI e telefonia, redes e operações.

Todos os assuntos relacionados a computação de usuário final, como a avaliação de prontidão dos computadores pessoais e dispositivos móveis para suportar os casos de uso comercial de Audioconferência, desde os requisitos de hardware até os requisitos de software, serão incluídos como parte da pesquisa do ambiente.

A pesquisa do ambiente também esclarece se há necessidade de [transferir os números de telefone para a Microsoft](https://support.office.com/article/Transfer-phone-numbers-to-Skype-for-Business-Online-47b3af8e-4171-4dec-8333-c956f108664e). Isso ajudará a sua organização a ajustar adequadamente o plano do projeto e preparar as informações necessárias para a portabilidade dos números. Você pode fazer a pesquisa do ambiente utilizado o seguinte [questionário](https://go.microsoft.com/fwlink/?linkid=858995).

A pesquisa do ambiente deve incluir avaliação da prontidão da rede para garantir que a rede esteja pronta para suportar a implementação do serviço de Audioconferência.

A prontidão da rede para suportar o serviço de Audioconferência pode ser determinada utilizando as informações coletadas através da pesquisa do ambiente (como detalhes da conectividade com a internet e topologia da WAN, links de sites, largura de banda disponível e dados de análise pessoal, que podem ser traduzidos para o uso esperado de cada carga de trabalho) na [ferramenta My Advisor Network Planner](https://go.microsoft.com/fwlink/?linkid=858999). Para confirmar a prontidão da rede, pode ser feita uma simulação de tráfego de mídia em tempo real usando as soluções fornecidas pela [Microsoft](https://go.microsoft.com/fwlink/?linkid=859002) ou pelos [parceiros das ferramentas de Avaliação da prontidão da rede](https://go.microsoft.com/fwlink/?linkid=859003).

Os resultados da avaliação da prontidão da rede darão uma ideia mais clara da otimização ou da remediação necessária da rede para o sucesso da implementação da Audioconferência.

A prontidão para a adoção pode ser avaliada através da execução de análise pessoal para criar uma lista de pessoas na organização que podem ser direcionadas para a implementação do serviço de Audioconferência. A análise pessoal inclui a identificação de periféricos adicionais ou dispositivos necessários para atingir os resultados comerciais pretendidos.

Fara fazer a análise pessoal, você pode conduzir um workshop envolvendo as partes envolvidas no projeto, utilizando o [deck de workshop Alinhamento Pessoal](https://go.microsoft.com/fwlink/?linkid=859005) e a [Matriz de características pessoais](https://go.microsoft.com/fwlink/?linkid=859006). O resultado do workshop de análise pessoal pode ser resumido em um relatório usando o modelo de [Relatório de análise pessoal](https://go.microsoft.com/fwlink/?linkid=859007).


> [!NOTE]
> Ao passo que os exemplos de Questionário de Descoberta e Análise Pessoal foram inicialmente escritos para o Skype for Business Online, a maioria do conteúdo é relevante para o Teams. Fique à vontade para modificar e remover itens que não são relevantes para os objetivos do projeto.


Você pode identificar riscos técnicos como parte da avaliação ambiental e da avaliação de prontidão para adoção, e desenvolver um plano de mitigação para cada risco identificado. Essas informações devem ser incorporadas como parte do plano de risco.

<a name="map-operational-roles"></a>Mapear funções operacionais
---------------------

O planejamento das operações e a identificação das equipes que operarão o serviço de Audioconferência é um passo importante, pois as operações devem ser iniciadas quando os primeiros usuários piloto estiverem habilitados. Cada uma das equipes identificadas precisa avaliar e chegar a um acordo quanto às tarefas e responsabilidades identificadas, e iniciar a preparação para operar o serviço de Audioconferência. A preparação pode incluir treinamentos e prontidão, pessoal adicional ou a certeza de que os provedores externos estão configurados para entregar o serviço.

<table>
<thead>
<tr class="header">
<th align="left">Função operacional</th>
<th align="left">Descrição</th>
<th align="left">Equipe</th>
<th align="left">Detalhes de contato</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Proprietário do serviço</td>
<td align="left">Proprietário do serviço, interface com as divisões da empresa, estratégia</td>
<td align="left">TBA</td>
<td align="left">TBA</td>
</tr>
<tr class="even">
<td align="left">Operações de Audioconferência</td>
<td align="left">Operações diárias, migração/adição/alteração de contas de usuários e dispositivos, monitoramento</td>
<td align="left">TBA</td>
<td align="left">TBA</td>
</tr>
<tr class="odd">
<td align="left">Administração de locatários</td>
<td align="left">Alterar configuração de todos os locatários, habilitar novos recursos</td>
<td align="left">TBA</td>
<td align="left">TBA</td>
</tr>
<tr class="even">
<td align="left">Central de atendimento</td>
<td align="left">Interface para os usuários finais obterem suporte</td>
<td align="left">TBA</td>
<td align="left">TBA</td>
</tr>
<tr class="odd">
<td align="left">Operações de rede</td>
<td align="left">Executa LAN, WAN, Wi-Fi e acesso à internet</td>
<td align="left">TBA</td>
<td align="left">TBA</td>
</tr>
<tr class="even">
<td align="left">Cliente &amp; Equipe de endpoints</td>
<td align="left">Gerenciar implantações de desktop</td>
<td align="left">TBA</td>
<td align="left">TBA</td>
</tr>
<tr class="odd">
<td align="left">Operações de identidade</td>
<td align="left">Gerenciar infraestrutura de identidade (AD, ADFS, Azure AD)</td>
<td align="left">TBA</td>
<td align="left">TBA</td>
</tr>
<tr class="even">
<td align="left">Gerenciamento de mudanças/adoção</td>
<td align="left">Gerenciar conscientização, treinamentos e adoção da solução</td>
<td align="left">TBA</td>
<td align="left">TBA</td>
</tr>
<tr class="odd">
<td align="left">Operações do Exchange</td>
<td align="left">Gerenciar o ambiente do Exchange</td>
<td align="left">TBA</td>
<td align="left">TBA</td>
</tr>
</tbody>
</table>

_Tabela 6 Exemplo de mapeamento de funções operacionais_


Para facilitar um mapeamento mais detalhado das funções operacionais, incluindo as tarefas associadas a cada uma das funções operacionais, você pode usar o [Pasta de trabalho de mapeamento de funções operacionais](https://www.skypeoperationsframework.com/Downloads?SelectedIDs=4_4_0_16) para coletar os detalhes que esclarecerão as funções e responsabilidades para suportar o serviço de Audioconferência.

<a name="document-success-plan"></a>Documentar plano de sucesso
---------------------

O plano de sucesso é a documentação criada na fase de Concepção, que consiste em caso de negócios, prontidão de serviço, plano de adoção e plano operacional.

O plano de sucesso fornecerá à equipe do projeto, que pode incluir FastTrack ou parceiro de implantação, informações suficientes para atingir os objetivos do serviço de Audioconferência da organização.

No geral, um plano de sucesso deve conter as seguintes seções principais:

-   Caso de negócios

-   Prontidão de serviço

-   Plano de adoção

-   Plano operacional

### <a name="business-case"></a>Caso de negócios

Casos de uso comercial, partes envolvidas, OKRs e KSIs, riscos e cronogramas do projeto geralmente compõem a maior parte das informações necessárias para um caso de negócios. Você precisa documentá-los como parte do plano de sucesso.

### <a name="service-readiness"></a>Prontidão de serviço

A avaliação do ambiente fornece as informações iniciais necessárias para determinar a prontidão técnica para a organização implementar a Audioconferência.

Aqui incluído está o plano para abordar as áreas que precisam de remediação descobertas através da avaliação do ambiente. Você precisa incluir a avaliação de prontidão de serviço e o plano de remediação como parte do plano de sucesso.

### <a name="adoption-plan"></a>Plano de adoção

Após a avaliação de prontidão para adoção, deve ser feito um planejamento detalhado adicional para que a equipe do projeto estabeleça um conjunto abrangente de planos de comunicação, plano de treinamento e atividades de adoção pré-lançamento, no lançamento e pós-lançamento.

Os recursos para dar suporte às atividades de adoção, como folhetos, e-mails de boas-vindas e materiais de treinamento, são identificados nesta etapa, juntamente com as personalizações necessárias para atender aos requisitos organizacionais.

Os modelos para as atividades de adoção estão disponíveis [aqui](https://www.microsoft.com/download/details.aspx?id=54244).

### <a name="operational-plan"></a>Plano operacional

O exercício de mapeamento de funções operacionais estabelecerá as funções, as responsabilidades,e as equipes designadas a cada função operacional para dar suporte à implementação da Audioconferência.

Você precisa inserir isso e incluir o plano operacional como parte do plano de sucesso para garantir a prontidão operacional da solução.

Planejamento da Audioconferência no Teams  <a name="Planning_AudioConferencing"> </a>
========================================

Para planejar a implementação da Audioconferência no Teams, uma série de decisões deve ser tomada antecipadamente para melhor preparar a sua organização para implementar uma solução que atenda aos requisitos da empresa. Essas decisões serão documentadas no plano de implementação técnica.

|  |  |
|---------|---------|
|  <iframe width="350" height="200" src="https://www.youtube.com/embed/AWbuvcWcYIc" frameborder="0" allowfullscreen></iframe>    | |


## <a name="availability-of-audio-conferencing"></a>Disponibilidade da Audioconferência

A Audioconferência está disponível nestes [países e regiões](https://support.office.com/article/Countries-and-regions-that-are-supported-for-Skype-for-Business-Online-PSTN-Services-6ba72f37-d303-4795-aa8f-7e1845078ed7?ui=en-US&rs=en-US&ad=US).


> [!IMPORTANT]
> Devido a restrições legais, para a Audioconferência estar disponível para organizações multinacionais, o contrato de assinaturas do Office 365 deve ser obtido dos países e regiões cobertos pelo serviço de Audioconferência.

Depois de confirmar a elegibilidade da sua organização para obter o serviço de Audioconferência, com base na lista de países e regiões disponíveis, compile a lista dos locais de usuários ou escritórios onde o serviço de Audioconferência será implementado.

<table>
<thead>
<tr class="header">
<td align="left"><img src="media/audio_conferencing_image7.png" /></td>
<td align="left">Pontos de decisão</td>
<td align="left"><p>Decida quais locais de usuários ou escritórios implementarão o serviço de Audioconferência.</p></td>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="media/audio_conferencing_image9.png" /></td>
<td align="left">Próximos passos</td>
<td align="left"><p>Documente os locais de usuários ou escritórios que implementarão o serviço de Audioconferência.</p></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<th align="left">Escritório</th>
<th align="left">Localização</th>
<th align="left">Serviço de Conferência PSTN</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">One Epping Road</td>
<td align="left">Austrália</td>
<td align="left">Audioconferência</td>
</tr>
<tr class="even">
<td align="left">100 Alma Road</td>
<td align="left">Hong Kong SAR</td>
<td align="left">Conferência PSTN herdada</td>
</tr>
<tr class="odd">
<td align="left">One Marina Boulevard</td>
<td align="left">Cingapura</td>
<td align="left">Audioconferência</td>
</tr>
<tr class="even">
<td align="left">32 London Bridge Street</td>
<td align="left">Reino Unido</td>
<td align="left">Audioconferência</td>
</tr>
<tr class="odd">
<td align="left">39 quai du Président Roosevelt</td>
<td align="left">França</td>
<td align="left">Audioconferência</td>
</tr>
</tbody>
</table>

_Tabela 7 Exemplo de lista de habilitação do site do serviço de Audioconferência_


## <a name="licensing-for-audio-conferencing"></a>Licença para a Audioconferência

[A licença para a Audioconferência](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7?ui=en-US&rs=en-US&ad=US), anteriormente conhecida como licença de Conferência PSTN do Skype for Business, está disponível como parte dos planos de inscrição Office 365 E5 ou como um complemento aos parte dos planos de inscrição Office 365 E1 ou Office 365 E3.

> [!NOTE]
> A conferência PSTN ou por discagem no Teams não suporta Provedores de Audioconferência<sup></sup> de terceiros (ACPs).
> <br>Se você já usa a Conferência PSTN do Skype for Business hoje, você pode aproveitar a Audioconferência no Teams imediatamente.

Para fornecer números de telefone gratuitos de ponte de conferência e para suportar discagem de conferência para números de telefone internacionais, você precisa configurar [Créditos de Comunicação](https://support.office.com/article/What-is-PSTN-Consumption-billing-524dbea7-117f-493d-8005-6461f7f10059) para a sua organização.


> [!IMPORTANT]
> Alguns países são atendidos apenas por números de telefone gratuitos para ponte de conferência, e nesse caso, o uso de Créditos de Comunicação é um requisito obrigatório para ter suporte de acesso a esses países.

A primeira consideração a fazer ao implementar os Créditos de Comunicação é decidir o valor inicial de fundos a serem comprados. Os valores de fundos recomendados podem ser consultados na documentação dos [Créditos de Comunicação](https://support.office.com/en-us/article/What-is-PSTN-Consumption-billing-524dbea7-117f-493d-8005-6461f7f10059).

Se a sua organização optar por usar recarga automática, uma recomendação sobre o gatilho (menor valor de fundos) também está incluída na documentação dos [Créditos de Comunicação](https://support.office.com/article/What-is-PSTN-Consumption-billing-524dbea7-117f-493d-8005-6461f7f10059). O valor da recarga automática deve ser determinado pelo uso real. O uso de Créditos de Comunicação deve ser monitorado ao longo do tempo e o valor da recarga precisa ser ajustado conforme a necessidade.

<table>
<thead>
<tr class="header">
<td align="left"><img src="media/audio_conferencing_image7.png" /></td>
<td align="left">Pontos de decisão</td>
<td align="left"><ul><li>Se a sua organização ainda não tiver adquirido a licença necessária para a Audioconferência, decida se as licenças da Audioconferência serão adquiridas ampliando as inscrições existentes do Office 365 ou adquirindo complementos de Audioconferência.</li>
<li>Decida se os Créditos de Comunicação serão obrigatórios para a implementação da Audioconferência. Em caso positivo, decida o valor inicial de fundos a serem comprados. Onde aplicável, decida o valor do gatilho e o valor da recarga automática.</li></ul></td>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="media/audio_conferencing_image9.png" /></td>
<td align="left">Próximos passos</td>
<td align="left"><ul><li>Documentar os usuários que receberão a licença da Audioconferência.</li>
<li>Documentar o plano de Créditos de Comunicação (valor inicial, valor do gatilho, valor da recarga automática).</li></ul></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<th align="left">Usuário</th>
<th align="left">Escritório</th>
<th align="left">Licença do Office 365</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Adele Vance</td>
<td align="left">One Epping Road</td>
<td align="left">Office 365 E5</td>
</tr>
<tr class="even">
<td align="left">Alex Wilber</td>
<td align="left">One Epping Road</td>
<td align="left">Office 365 E3, complemento de Audioconferência</td>
</tr>
<tr class="odd">
<td align="left">Ben Walters</td>
<td align="left">One Epping Road</td>
<td align="left">Office 365 E3, complemento de Audioconferência</td>
</tr>
<tr class="even">
<td align="left">Christie Cline</td>
<td align="left">One Marina Boulevard</td>
<td align="left">Office 365 E3, complemento de Audioconferência</td>
</tr>
<tr class="odd">
<td align="left">Debra Berger</td>
<td align="left">One Marina Boulevard</td>
<td align="left">Office 365 E5</td>
</tr>
<tr class="even">
<td align="left">Lee Gu</td>
<td align="left">One Marina Boulevard</td>
<td align="left">Office 365 E5</td>
</tr>
<tr class="odd">
<td align="left">Emily Braun</td>
<td align="left">32 London Bridge Street</td>
<td align="left">Office 365 E5</td>
</tr>
<tr class="even">
<td align="left">Lidia Holloway</td>
<td align="left">32 London Bridge Street</td>
<td align="left">Office 365 E5</td>
</tr>
<tr class="odd">
<td align="left">Pradeep Gupta</td>
<td align="left">32 London Bridge Street</td>
<td align="left">Office 365 E5</td>
</tr>
<tr class="even">
<td align="left">Marcel Beauchamp</td>
<td align="left">39 quai du Président Roosevelt</td>
<td align="left">Office 365 E3, complemento de Audioconferência</td>
</tr>
<tr class="odd">
<td align="left">Rachelle Cormier</td>
<td align="left">39 quai du Président Roosevelt</td>
<td align="left">Office 365 E5</td>
</tr>
<tr class="even">
<td align="left">Isabell Potvin</td>
<td align="left">39 quai du Président Roosevelt</td>
<td align="left">Office 365 E3, complemento de Audioconferência</td>
</tr>
</tbody>
</table>

_Tabela 8 Exemplo de lista de atribuição de licenças para organizadores de reunião de Audioconferência_

<table>
<thead>
<tr class="header">
<th align="left">Valor inicial</th>
<td align="left">US$ 1.000</td>
</tr>
</thead>
<thead>
<tr class="header">
<th align="left">Valor do gatilho</th>
<td align="left">US$ 400</td>
</tr>
<tr class="header">
<th align="left">Valor da recarga automática</th>
<td align="left">TBA</td>
</tr>
</tbody>
</table>

_Tabela 9 Exemplo de números de planejamento de Créditos de Comunicação_


## <a name="conference-bridge-phone-numbers"></a>Números de telefone de ponte de conferência

O serviço de Audioconferência do Office 365 inclui:

-   Vários tipos de números de telefone de ponte de conferência (pagos e gratuitos)

-   Várias categorias de número de telefone (exclusivo e compartilhado)

-   Suporte de vários idiomas para a ponte de conferência (primária e secundária)

-   Um número de telefone padrão para o locatário.

A descrição completa dos recursos incluídos pode ser consultada em [Configurar conferência PSTN ou por discagem para o Skype for Business](https://support.office.com/article/Set-up-dial-in-or-PSTN-conferencing-for-Skype-for-Business-d01954f1-4f37-4cf5-a636-20039e5c59e9?ui=en-US&rs=en-US&ad=US) e [Números de telefone para conferência de discagem](https://support.office.com/article/Phone-numbers-for-dial-in-conferencing-95a08f84-04e5-4f72-88a8-d6472a7c89d7?ui=en-US&rs=en-US&ad=US)**.**

> [!NOTE]
> Os números de telefone exclusivos da ponte de conferência são contados em relação ao limite de números de telefone que podem ser adquiridos por locatário com base no número de licenças aplicáveis,conforme descrito em [Obter números de telefone para o serviço Skype for Business](https://support.office.com/article/Getting-Skype-for-Business-service-phone-numbers-e434aeb2-af99-40e7-981e-a474f0383734). Os números de telefone gratuitos da ponte de conferência não precisam de Créditos de Comunicação.

Se houver números de telefone existentes da ponte de conferência que precisem ser transferidos para o serviço de Audioconferência, presumindo que estejam cumprindo os requisitos específicos do país, os números de telefone da ponte de conferência existentes poderão ser transferidos para a Microsoft.


> [!NOTE]
> A complexidade da transferência de números de telefone para a Microsoft varia muito com base nos países ou regiões, operadoras, o número de circuitos envolvidos e vários outros fatores. Para planejar a portabilidade dos números de telefone, consulte o [Guia de portabilidade de números](https://go.microsoft.com/fwlink/?linkid=859011).

|  |  |
|---------|---------|
| <iframe width="350" height="200" src="https://www.youtube.com/embed/5k0C21KAsns" frameborder="0" allowfullscreen></iframe>  |  |

Detalhes adicionais sobre a transferência de números de telefone para o serviço de Audioconferência podem ser encontrados em [Transferir números de telefone para o Skype for Business Online](https://support.office.com/article/Transfer-phone-numbers-to-Skype-for-Business-Online-47b3af8e-4171-4dec-8333-c956f108664e).

<table>
<thead>
<tr class="header">
<td align="left"><img src="media/audio_conferencing_image7.png" /></td>
<td align="left">Pontos de decisão</td>
<td align="left"><ul><li>Decidir se a organização exigirá números de telefone exclusivos da ponte de conferência</li>
<li>Decidir como os números de telefone exclusivos da ponte da conferência serão obtidos para locais de usuários ou escritórios que estão no escopo de implementação da Audioconferência (obter da Microsoft ou transferir os números de telefone existentes)</li>
<li>Se você optar por obter da Microsoft, decidir o método para obter números de telefone (envio de formulários ou automatizado) para os locais de usuários ou escritórios que estão no escopo de implementação da Audioconferência</li>
<li>Decidir as preferências de idioma a ser configuradas para naca números de telefone de ponte de conferência</li>
<li>Decidir o número de telefone de ponte de conferência padrão do locatário</li></ul></td>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="media/audio_conferencing_image9.png" /></td>
<td align="left">Próximos passos</td>
<td align="left"><ul><li>Documentar o plano mestre para a aquisição de números de telefone, detalhando como os números de telefone serão obtidos para cada um dos locais de usuários ou escritórios que estão no escopo de implementação da Audioconferência.</li>
<li>Se aplicável, preencha <a href="https://support.office.com/article/Get-phone-numbers-for-Skype-for-Business-Online-6b61cb3c-361c-48a8-a9ef-d81bddde27bb?ui=en-US&amp;rs=en-US&amp;ad=US">o formulário de solicitação de novo número de telefone</a>, um formulário para cada local ou escritório</li>
<li>Se você optar por transferir números de telefone existentes confira o <a href="https://go.microsoft.com/fwlink/?linkid=859011">Guia de portabilidade de números</a> para planejar a ajustar o cronograma de implementação da Audioconferência de acordo.</li>
<li>Documentar as configurações detalhadas do número de telefone da ponte de conferência (números de telefone exclusivos e compartilhados da ponte de conferência, preferências de idioma para cada número exclusivo de telefone da ponte de conferência, número de telefone da ponte de conferência padrão do locatário)</li></ul></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<th align="left">Escritório</th>
<th align="left">Aquisição do número da ponte e Tipo da ponte</th>
<th align="left">Número da ponte</th>
<th align="left">Idioma da ponte</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">One Epping Road</td>
<td align="left">Adquirir novo, exclusivo</td>
<td align="left">TBA</td>
<td align="left">Inglês (Austrália)</td>
</tr>
<tr class="even">
<td align="left">One Marina Boulevard</td>
<td align="left">Adquirir novo, compartilhado</td>
<td align="left">TBA</td>
<td align="left">Inglês (Estados Unidos); Chinês (Simplificado, PRC)</td>
</tr>
<tr class="odd">
<td align="left">32 London Bridge Street</td>
<td align="left">Porta existente, exclusiva</td>
<td align="left">+44 20 7946 0001</td>
<td align="left">Inglês (Reino Unido)</td>
</tr>
<tr class="even">
<td align="left">39 quai du Président Roosevelt</td>
<td align="left">Adquirir novo, exclusivo</td>
<td align="left">TBA</td>
<td align="left">Francês (França), Inglês (Reino Unido)</td>
</tr>
</tbody>
</table>

_Tabela 10 Exemplo de detalhes de ponte de conferência_


> [!NOTE]
> A tabela de exemplo acima e as tabelas subsequentes ao longo deste documento servem como modelo. Você verá “TBA” (a ser adicionado) para informações que você precisa inserir como parte do seu processo de planejamento.

## <a name="conference-bridge-settings"></a>Configurações de ponte de conferência

As opções de configuração da experiência de entrar em uma reunião de Audioconferência em toda a organização (notificação de entrada e saída e gravação de nome do chamador), o comprimento do PIN do organizador da reunião e a notificação por e-mail estão disponíveis para adaptar melhor a experiência do usuário final.

-   As notificações de entrada e saída de reuniões estão disponíveis na forma de nome, número de telefone e tons registrados.

-   O comprimento do PIN pode ter de 4 a 12 dígitos, com um PIN de 5 dígitos como padrão.

-   Os e-mails de notificação após a habilitação da licença de Audioconferência ou qualquer outra alteração conduzida pelo administrador estão habilitados por padrão. Você pode desabilitar esse recurso e assumir o controle das comunicações dos usuários finais da sua organização.

Para os usuários aos quais tenha sido atribuída uma licença de Audioconferência, os números chamada pagos e gratuitos padrão, mostrados nas coordenadas de Audioconferência, podem ser configurados para uso:

-   no padrão em nível de locatário ou

-   em números de telefone de ponte de conferência atribuídos automaticamente ou

-   em números de telefone de ponte de conferência definidos manualmente para cada usuário.

Os números de telefone da ponte de conferência específicos do usuário costumam ser úteis em organizações nacionais ou internacionais, onde os usuários são distribuídos e precisam fornecer números locais como números de telefone da ponte de conferência padrão nos convites de reunião.

Os participantes que entram de diferentes cidades ou do exterior podem procurar números adicionais configurados no nível do locatário, mas esses números não aparecem diretamente nos convites de reunião. Os convites de reunião contêm um link que levará os participantes à página de números de discagem da conferência do Teams para que eles procurem os números de telefone da ponte de conferência mais próximos do seu local que estejam disponíveis.

Você também pode configurar como os autores de chamada não autenticados são tratados por cada organizador de reunião individual para exigir que o organizador da reunião inicie a reunião antes que os autores de chamada não autenticados sejam admitidos ou para permitir que os autores de chamada não autenticados iniciem uma reunião.

Estão disponíveis configurações adicionais que podem ser aplicadas para cada usuário para controlar o uso de números de telefone gratuitos de ponte de conferência e discagem de uma conferência.

> [!NOTE]
> Esses controles relacionados a custo estão atualmente disponíveis somente para clientes da prévia. Você pode inscrever a sua organização no programa de prévia em [https://www.skypepreview.com](https://go.microsoft.com/fwlink/?linkid=859013).

Com esses controles, você pode decidir se os organizadores da reunião podem fornecer números de telefone gratuitos de ponte de conferência para reuniões organizadas por eles, ou para controlar se os participantes podem discar das reuniões organizadas por eles. O nível de controle de discagem vai da exclusão da permissão de discagem, permitindo discar apenas para números domésticos, até a permissão de discagem para números domésticos e internacionais.

<table>
<thead>
<tr class="header">
<td align="left"><img src="media/audio_conferencing_image7.png" /></td>
<td align="left">Pontos de decisão</td>
<td align="left"><ul><li>Decidir se a organização exigirá notificações de entrada e saída e, em caso afirmativo, o tipo de notificação a ser implementada (tons, número de telefone ou nome registrado).</li>
<li>Decidir o comprimento do PIN da Audioconferência que atenda às exigências de segurança da organização.</li>
<li>Decidir se a organização deseja assumir o controle das comunicações do usuário final relacionadas ao serviço de Audioconferência.</li>
<li>Decidir os números de telefone da ponte da conferência a serem atribuídos a cada organizador de reunião.</li>
<li>Decidir se alguns organizadores de reunião exigirão o recurso de usar números de telefone gratuitos de ponte de conferência para as suas reuniões</li>
<li>Decidir se alguns organizadores de reunião exigirão o recurso de permitir que os autores da chamada não autenticados iniciem uma reunião.</li>
<li>Decidir se alguns organizadores de reunião exigirão que a discagem de saída da conferência seja controlada.</li></ul></td>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="media/audio_conferencing_image9.png" /></td>
<td align="left">Próximos passos</td>
<td align="left"><ul><li>Documentar detalhadamente as configurações de ponte de conferência (notificações de entrada e saída, comprimento do PIN, notificação por e-mail de alteração do configurações).</li>
<li>Documentar os números de telefone de ponte de conferência a serem atribuídos a cada organizador de reunião na configuração correspondente para controlar a política de autores de chamada não autenticados e os controles gratuitos e de discagem de saída.</li></ul></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<td align="left"><strong>Habilitar notificações de entrada e saída de reuniões</strong></td>
<td align="left">Habilitado</td>
</tr>
</thead>
<thead>
<tr class="header">
<td align="left"><strong>Tipo de anúncio de entrada/saída</strong></td>
<td align="left">Tons</td>
</tr>
<tr class="header">
<td align="left"><strong>Solicitar que os autores da chamada registrem seu nome antes de entrar na reunião</strong></td>
<td align="left">Desabilitado</td>
</tr>
<tr class="header">
<td align="left"><strong>Tamanho mínimo do PIN</strong></td>
<td align="left">5</td>
</tr>
<tr class="header">
<td align="left"><strong>Enviar e-mails automaticamente aos usuários se suas configurações de discagem forem alteradas</strong></td>
<td align="left">Desabilitado</td>
</tr>
</tbody>
</table>

_Tabela 11 Exemplo de configurações de ponte de conferência_


<table>
<thead>
<tr class="header">
<th align="left">Usuário</th>
<th align="left">Escritório</th>
<th align="left">Número de chamada padrão</th>
<th align="left">Número de chamada gratuita padrão</th>
<th align="left">Permitir chamada gratuita</th>
<th align="left">Autores de chamada não autenticados ignoram o lobby</th>
<th align="left">Discagem de saída de conferência</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Adele Vance</td>
<td align="left">One Epping Road</td>
<td align="left">TBA</td>
<td align="left">TBA</td>
<td align="left">Sim</td>
<td align="left">Habilitado</td>
<td align="left">Doméstico e internacional</td>
</tr>
<tr class="even">
<td align="left">Alex Wilber</td>
<td align="left">One Epping Road</td>
<td align="left">TBA</td>
<td align="left">TBA</td>
<td align="left">Não</td>
<td align="left">Desabilitado</td>
<td align="left">Não permitido</td>
</tr>
<tr class="odd">
<td align="left">Ben Walters</td>
<td align="left">One Epping Road</td>
<td align="left">TBA</td>
<td align="left">TBA</td>
<td align="left">Não</td>
<td align="left">Desabilitado</td>
<td align="left">Não permitido</td>
</tr>
<tr class="even">
<td align="left">Christie Cline</td>
<td align="left">One Marina Boulevard</td>
<td align="left">TBA</td>
<td align="left">TBA</td>
<td align="left">Sim</td>
<td align="left">Desabilitado</td>
<td align="left">Doméstico</td>
</tr>
<tr class="odd">
<td align="left">Debra Berger</td>
<td align="left">One Marina Boulevard</td>
<td align="left">TBA</td>
<td align="left">TBA</td>
<td align="left">Sim</td>
<td align="left">Habilitado</td>
<td align="left">Doméstico</td>
</tr>
<tr class="even">
<td align="left">Lee Gu</td>
<td align="left">One Marina Boulevard</td>
<td align="left">TBA</td>
<td align="left">TBA</td>
<td align="left">Sim</td>
<td align="left">Habilitado</td>
<td align="left">Doméstico</td>
</tr>
<tr class="odd">
<td align="left">Emily Braun</td>
<td align="left">32 London Bridge Street</td>
<td align="left">+44 20 7946 0001</td>
<td align="left">TBA</td>
<td align="left">Sim</td>
<td align="left">Habilitado</td>
<td align="left">Não permitido</td>
</tr>
<tr class="even">
<td align="left">Lidia Holloway</td>
<td align="left">32 London Bridge Street</td>
<td align="left">+44 20 7946 0001</td>
<td align="left">TBA</td>
<td align="left">Sim</td>
<td align="left">Desabilitado</td>
<td align="left">Não permitido</td>
</tr>
<tr class="odd">
<td align="left">Pradeep Gupta</td>
<td align="left">32 London Bridge Street</td>
<td align="left">+44 20 7946 0001</td>
<td align="left">TBA</td>
<td align="left">Sim</td>
<td align="left">Desabilitado</td>
<td align="left">Não permitido</td>
</tr>
<tr class="even">
<td align="left">Marcel Beauchamp</td>
<td align="left">39 quai du Président Roosevelt</td>
<td align="left">TBA</td>
<td align="left">TBA</td>
<td align="left">Não</td>
<td align="left">Desabilitado</td>
<td align="left">Doméstico</td>
</tr>
<tr class="odd">
<td align="left">Rachelle Cormier</td>
<td align="left">39 quai du Président Roosevelt</td>
<td align="left">TBA</td>
<td align="left">TBA</td>
<td align="left">Sim</td>
<td align="left">Habilitado</td>
<td align="left">Doméstico e internacional</td>
</tr>
<tr class="even">
<td align="left">Isabell Potvin</td>
<td align="left">39 quai du Président Roosevelt</td>
<td align="left">TBA</td>
<td align="left">TBA</td>
<td align="left">Não</td>
<td align="left">Desabilitado</td>
<td align="left">Doméstico</td>
</tr>
</tbody>
</table>

_Tabela 12 Exemplo de atribuições de configurações de ponte de conferência_


## <a name="dial-plans"></a>Planos de discagem

O [Plano de discagem](https://support.office.com/article/What-are-PSTN-Calling-dial-plans-2f0cfb59-1ca1-4e31-84ce-09d0b1a7ce1b), um Sistema de Telefonia do Office 365, é um conjunto de regras de normalização que converte números telefônicos discados em um formato alternativo (normalmente no formato[E.164](https://go.microsoft.com/fwlink/?linkid=859014)) para autorização de chamada e roteamento de chamada. O serviço de Audioconferência aproveita os mesmos recursos usados pelo Sistema de Telefonia para converter números de telefone discados em cenários de discagem de saída de conferência.

Um plano de discagem permite que os usuários disquem números de telefone da forma como estão acostumados, como omitir o código de área para chamadas locais, omitir o código de país para chamadas domésticas ou mesmo usar atalhos de discagem ao fazer uma discagem de saída de conferência.

Dentro do recurso Sistema de Telefonia do Office 365, existem dois tipos de planos de discagem:

-   **Plano de discagem para serviço**. Esse é o plano de discagem padrão, é aplicado aos usuários com base no local de uso do Office 365 e não pode ser modificado.

<!-- -->

-   **Plano de discagem para locatários**. Esse é um plano de discagem personalizável em um locatário e é dividido em mais dois tipos:

    -   **Plano de discagem para locatário global** – o plano de discagem se aplica para todos os usuários do locatário.

    -   **Plano de discagem para locatário usuário** – o plano de discagem se aplica apenas a usuários específicos.


> [!NOTE]
> Confira a documentação dos [planos de discagem do Plano de Chamadas do Office 365](https://support.office.com/article/What-are-PSTN-Calling-dial-plans-2f0cfb59-1ca1-4e31-84ce-09d0b1a7ce1b) pata obter exemplos e mais detalhes.

O plano de discagem efetivo atribuído aos usuários é a combinação do plano de discagem para serviço (com base no local de uso do Office 365 do usuário) e do plano de discagem para locatários (que pode ser o plano de discagem para locatário global ou o plano de discagem para locatário usuário).

![](media/audio_conferencing_image8.png)

Há um máximo de 25 regras de normalização em cada plano de discagem para locatários e, portanto, a duplicação das regras de normalização já disponíveis como parte do plano de discagem para serviço precisa ser evitada.

<table>
<thead>
<tr class="header">
<td align="left"><img src="media/audio_conferencing_image7.png" /></td>
<td align="left">Pontos de decisão</td>
<td align="left"><ul><li>Decida se sua organização exigirá planos de discagem personalizados (requisitos de negócios, requisitos de adoção, etc.).</li>
<li>Se aplicável, decidir o escopo do plano de discagem para locatários (locatário global ou locatário usuário) para ter suporte para os requisitos dos planos de discagem personalizados.</li>
<li>Se aplicável, decidir os planos de discagem para locatários que serão criados para oferecer suporte para locais de usuários ou escritórios que estejam no escopo de implementação da Audioconferência.</li>
<li>Se aplicável, decidir qual usuário exigirá um plano de discagem personalizado e o plano de discagem para locatários a ser atribuído para cada usuário.</li></ul></td>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="media/audio_conferencing_image9.png" /></td>
<td align="left">Próximos passos</td>
<td align="left"><ul><li>Documentar os planos de discagem personalizados e as regras de normalização associadas a serem configuradas como parte da implementação da Audioconferência.</li>
<li>Documentar os usuários aos quais serão atribuídos um plano de discagem personalizado e o plano de discagem para locatários a ser atribuído para cada usuário.</li></ul></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<th align="left">Nome/descrição do plano de discagem para locatários</th>
<th align="left">Nome/descrição das regras de normalização</th>
<th align="left">Padrão</th>
<th align="left">Conversão</th>
<th align="left">IsInternalExtension</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>AU-NSW-NorthRyde-OER</strong></p>
<p><em>One Epping Road North Ryde, NSW, AU Dial Plan</em></p></td>
<td align="left"><p><strong>AU-NSW-NorthRyde-OER-Internal</strong></p>
<p><em>Número interno (x7000 - x7999) para o escritório de One Epping Road, North Ryde, NSW, Austrália</em></p></td>
<td align="left">^(7\d{3})$</td>
<td align="left">+6125550$1</td>
<td align="left">True</td>
</tr>
<tr class="even">
<td align="left"></td>
<td align="left"><p><strong>AU-NSW-Local</strong></p>
<p><em>Normalização do número local para NSW, Austrália</em></p></td>
<td align="left">^([2-9]\d{7})$</td>
<td align="left">+612$1</td>
<td align="left">False</td>
</tr>
<tr class="odd">
<td align="left"></td>
<td align="left"><p><strong>AU-TollFree</strong></p>
<p><em>Normalização de número gratuito na Austrália</em></p></td>
<td align="left">^(1[38]\d{4,8})\d*$</td>
<td align="left">+61$1</td>
<td align="left">False</td>
</tr>
<tr class="even">
<td align="left"></td>
<td align="left"><p><strong>AU-Service</strong></p>
<p><em>Normalização de número de serviço na Austrália</em></p></td>
<td align="left">^(000|1[0125]\d{1,8})$</td>
<td align="left">$1</td>
<td align="left">False</td>
</tr>
<tr class="odd">
<td align="left"><p><strong>SG-Singapore-OMB</strong></p>
<p><em>OMB Singapore, SG Dial Plan</em></p></td>
<td align="left"><p><strong>SG-OMB-Internal</strong></p>
<p><em>Número interno (x8000 – x8999) para o escritório OMB, Cingapura</em></p></td>
<td align="left">^(8\d{3})$</td>
<td align="left">+656888$1</td>
<td align="left">True</td>
</tr>
<tr class="even">
<td align="left"></td>
<td align="left"><p><strong>SG-TollFree</strong></p>
<p><em>Normalização de número gratuito em Cingapura</em></p></td>
<td align="left">^(1?800\d{7})\d*$</td>
<td align="left">+65$1</td>
<td align="left">False</td>
</tr>
<tr class="odd">
<td align="left"></td>
<td align="left"><p><strong>SG-Service</strong></p>
<p><em>Normalização de número de serviço em Cingapura</em></p></td>
<td align="left">^(1\d{3,4}|9\d{2})$</td>
<td align="left">$1</td>
<td align="left">False</td>
</tr>
<tr class="even">
<td align="left"><p><strong>FR-Paris-Issy-39qdPR</strong></p>
<p><em>39 quai du Président Roosevelt Issy-les-Moulineaux, France Dial Plan</em></p></td>
<td align="left"><p><strong>FR-39qdPR-Internal</strong></p>
<p><em>Número interno (x7000 – x7999) para o escritório de 39 quai du Président Roosevelt, Issy-les-Moulineaux, França</em></p></td>
<td align="left">^(7\d{3})$</td>
<td align="left">+3319999$1</td>
<td align="left">True</td>
</tr>
<tr class="odd">
<td align="left"></td>
<td align="left"><p><strong>FR-TollFree</strong></p>
<p><em>Normalização de número gratuito na França</em></p></td>
<td align="left">^0?(80\d{7})\d*$</td>
<td align="left">+33$1</td>
<td align="left">False</td>
</tr>
<tr class="even">
<td align="left"></td>
<td align="left"><p><strong>FR-Service</strong></p>
<p><em>Normalização de número de serviço na França</em></p></td>
<td align="left"><p>^(1\d{1,2}|11[68]\d{3}|</p>
<p>10\d{2}|3\d{3})$</p></td>
<td align="left">$1</td>
<td align="left">False</td>
</tr>
</tbody>
</table>

_Tabela 13 Exemplo de planos de discagem para locatários_


<table>
<thead>
<tr class="header">
<th align="left">Usuário</th>
<th align="left">Escritório</th>
<th align="left">Tipo do plano de discagem</th>
<th align="left">Nome do plano de discagem</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Adele Vance</td>
<td align="left">One Epping Road</td>
<td align="left">Plano de discagem para locatários</td>
<td align="left">AU-NSW-NorthRyde-OER</td>
</tr>
<tr class="even">
<td align="left">Alex Wilber</td>
<td align="left">One Epping Road</td>
<td align="left">Plano de discagem para locatários</td>
<td align="left">AU-NSW-NorthRyde-OER</td>
</tr>
<tr class="odd">
<td align="left">Ben Walters</td>
<td align="left">One Epping Road</td>
<td align="left">Plano de discagem para locatários</td>
<td align="left">AU-NSW-NorthRyde-OER</td>
</tr>
<tr class="even">
<td align="left">Christie Cline</td>
<td align="left">One Marina Boulevard</td>
<td align="left">Plano de discagem para locatários</td>
<td align="left">SG-Singapore-OMB</td>
</tr>
<tr class="odd">
<td align="left">Debra Berger</td>
<td align="left">One Marina Boulevard</td>
<td align="left">Plano de discagem para locatários</td>
<td align="left">SG-Singapore-OMB</td>
</tr>
<tr class="even">
<td align="left">Lee Gu</td>
<td align="left">One Marina Boulevard</td>
<td align="left">Plano de discagem para locatários</td>
<td align="left">SG-Singapore-OMB</td>
</tr>
<tr class="odd">
<td align="left">Emily Braun</td>
<td align="left">32 London Bridge Street</td>
<td align="left">Plano de discagem para serviço</td>
<td align="left">N/A</td>
</tr>
<tr class="even">
<td align="left">Lidia Holloway</td>
<td align="left">32 London Bridge Street</td>
<td align="left">Plano de discagem para serviço</td>
<td align="left">N/A</td>
</tr>
<tr class="odd">
<td align="left">Pradeep Gupta</td>
<td align="left">32 London Bridge Street</td>
<td align="left">Plano de discagem para serviço</td>
<td align="left">N/A</td>
</tr>
<tr class="even">
<td align="left">Marcel Beauchamp</td>
<td align="left">39 quai du Président Roosevelt</td>
<td align="left">Plano de discagem para locatários</td>
<td align="left">FR-Paris-Issy-39qdPR</td>
</tr>
<tr class="odd">
<td align="left">Rachelle Cormier</td>
<td align="left">39 quai du Président Roosevelt</td>
<td align="left">Plano de discagem para locatários</td>
<td align="left">FR-Paris-Issy-39qdPR</td>
</tr>
<tr class="even">
<td align="left">Isabell Potvin</td>
<td align="left">39 quai du Président Roosevelt</td>
<td align="left">Plano de discagem para locatários</td>
<td align="left">FR-Paris-Issy-39qdPR</td>
</tr>
</tbody>
</table>

_Tabela 14 Exemplo de atribuições de planos de discagem_


## <a name="microsoft-teams-configurations"></a>Configurações do Microsoft Teams

Uma vez que a Audioconferência está disponível apenas para reuniões agendadas, as configurações de nível de locatário que regem o agendamento de reuniões (reuniões privadas e de canal) devem estar habilitadas.


> [!NOTE]
> No momento, se sua organização tiver exigências de conformidade para garantir que todas as discussões nas reuniões sejam detectáveis, é necessário desabilitar as reuniões privadas se o organizador tiver uma caixa de correio no Exchange.<br><br>
> Em outro caso de uso, se todas as reuniões da organização tiverem que permanecer visíveis apenas <strong>para as partes convidadas</strong>, recomendamos que você desabilite a possibilidade de agendar reuniões nos <strong>canais</strong> para evitar a divulgação das informações da reunião para as partes que não foram convidadas.

As configurações, disponíveis como configurações em nível de locatário, são aplicáveis para todos os usuários da organização e afetarão todas as reuniões agendadas no Teams, não especificamente as reuniões Teams **com** Audioconferência.

<table>
<thead>
<tr class="header">
<td align="left"><img src="media/audio_conferencing_image7.png" /></td>
<td align="left">Ponto de decisão</td>
<td align="left"><p>Decidir se a organização exigirá ativar ou desativar o agendamento de reuniões privadas.</p>
<p>Decidir se a organização exigirá ativar ou desativar o agendamento de reuniões de canal.</p></td>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="media/audio_conferencing_image9.png" /></td>
<td align="left">Próximos passos</td>
<td align="left"><p>Documentar as configurações de agendamento de reuniões para o Teams.</p></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<td align="left"><strong>Permitir agendamento de reuniões privadas</strong></td>
<td align="left">Habilitado</td>
</tr>
</thead>
<thead>
<tr class="odd">
<td align="left"><strong>Permitir agendamento de reuniões de canal</strong></td>
<td align="left">Desabilitado</td>
</tr>
</tbody>
</table>

_Tabela 15 Exemplo de configurações de reuniões Microsoft Teams_


## <a name="document-technical-implementation-plan"></a>Documentar o plano de implementação técnica

Utilizar os pontos de decisão acima para documentar o seu plano de implementação técnica.

Esse plano de implementação técnica fornecerá à equipe do projeto, que pode incluir o FastTrack ou um parceiro de implantação, as informações necessárias para executar a integração técnica para a implementação da Audioconferência.

No geral, um plano de implementação técnica deve conter as seguintes seções principais:

-   Lista de habilitação do site do serviço de Audioconferência

-   Lista de atribuição de licenças para organizadores de reunião de Audioconferência

-   Número de planejamento de Créditos de Comunicação

-   Detalhes de ponte de conferência

-   Configurações de ponte de conferência

-   Atribuições das configurações de ponte de conferência

-   Planos de discagem para locatários

-   Atribuições de planos de discagem

-   Configurações de reuniões Microsoft Teams

Com a conclusão do plano de sucesso e do plano de implementação técnica, agora você está pronto para conduzir a sua organização para as próximas etapas da jornada do cliente do Office 365.

<a name="onboard"></a>Integração
=======

*Em breve.*

<a name="drive-value"></a>Gerar valor
===========

*Em breve.*



### <a name="see-also"></a>Consulte também
[Configurar conferência PSTN ou de discagem para o Skype for Business](https://support.office.com/article/Set-up-audio-conferencing-for-Skype-for-Business-and-Microsoft-Teams-d01954f1-4f37-4cf5-a636-20039e5c59e9)
