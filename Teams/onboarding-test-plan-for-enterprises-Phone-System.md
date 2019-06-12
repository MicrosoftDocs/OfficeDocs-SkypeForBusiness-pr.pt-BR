---
title: Plano de teste corporativo para Sistema de Telefonia com Planos de Chamadas no Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Confirme se as expectativas da sua organização são atendidas por meio do teste do sistema de telefonia em recursos, funcionalidade e usabilidade do teams.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1534c1b327e7fda146894430ca750f01c53e8fa4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33898750"
---
<a name="define-and-document-your-phone-system-with-calling-plans-in-teams-test-plan-for-enterprises"></a>Definir e documentar o sistema telefônico com planos de chamada no plano de teste do teams para empresas 
============================================================================================

Depois de definir e documentar seu sistema telefônico com planos de chamada no sucesso do teams Business e planos de implementação técnica como parte da fase enVision, a próxima etapa é validar que as expectativas e os requisitos da sua organização são atendidos recurso, funcionalidade e usabilidade. Você deve executar esta etapa de validação antes de implantar uma implantação piloto ou final em seu ambiente de produção.

Você pode aproveitar o plano de sucesso para empresas definido durante a fase do enVision para servir como base para determinar as atividades, expectativas, recursos/casos de teste de funcionalidade e escopo geral a serem avaliados durante a fase de teste.

<a name="identify-testing-support-stakeholders"></a>Identificar participantes do suporte de teste
-------------------------------------

Ao preparar-se para avaliar o sistema telefônico com recursos de planos de chamada, crie uma matriz de suporte de teste para identificar as funções necessárias para dar suporte à fase de teste.

> [!TIP]
> Ao preencher a matriz de participantes do suporte de teste do Teams, você pode ver que algumas funções são iguais às identificadas durante a fase do enVision, mas com descrições de função inclinadas em direção ao teste. Talvez seja necessário identificar funções adicionais, dependendo dos requisitos exclusivos de seus cenários de teste.

#### <a name="teams-testing-support-stakeholder-matrix"></a>Suporte ao teste de equipe matriz de participantes

> [!TIP]
> 
> Veja a seguir um exemplo de um modelo de suporte de teste dos interessados que você pode usar para documentar quais interessados você precisa para dar suporte à fase de teste.

| Função                          | Descrição da função                                                                                                                                                                          | Recurso atribuído, informações de contato e local |
|-------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------|
| Testando o patrocinador executivo (es)  | <ul><li>Garanta que os recursos da equipe atendam às necessidades comerciais; os patrocinadores executivos são fluentes nos resultados essenciais dos negócios e nos cenários de uso priorizado.</li><li>Servir como autoridade final e assumir a responsabilização para objetivos de recursos de equipe do teams.</li><li>Ajude a solucionar os problemas redimensionados pelo líder do teste.</li><li>A comunicação do patrocinador na empresa sobre metas de teste.</li><li>Seja responsável por fazer decisões estratégicas importantes.</li><li>Seja responsável por garantir a disponibilidade de recursos obrigatórios e orçamento para os esforços de teste de suporte.</li><li>Reconhecimento e aquisição de drive para a campanha de teste com outros interessados importantes.</li><li>Serve como patrocinador de teste durante a fase de avaliação de teste.</li></ul>                                                 | A ser determinado                                                  |
| Direcionando membros do Comitê    | <ul><li>Mantenha interesse em e forneça orientações para a direção geral do sistema telefônico com a implantação de serviços de planos de chamada.<li>Ajudar na divulgar estratégica ao impulsionar a compra em toda a organização.</li></ul>                                                                        | A ser determinado                                                  |
| Líder de projeto                  |<ul><li> Gerenciar e conduzir a equipe do projeto.</li><li>Coordene parceiros e equipes de trabalho envolvidos no projeto.</li><li>Seja possível para criar e gerenciar planos de projeto para atender a resultados trimestrais de chave.</li><li>Solucionar problemas de funcionalidade interfuncional.</li><li>Forneça atualizações regulares para os patrocinadores do projeto.</li><li>Incorpore ao plano de adoção geral do usuário as informações importantes sobre a experiência do usuário identificadas nos resultados do teste.</li><li>Liderar análises mensais de negócios e operacionais, contribuir para análises trimestrais dos negócios.</li></ul>                                                                                                                                                         | A ser determinado                                                  |
| Líder/arquiteto de colaboração  | <ul><li>Seja responsável pela execução na estratégia de colaboração definida pelos executivos da empresa.</li><li>Analise e escolha produtos de colaboração para a empresa que atenda às metas de negócios.</li><li>Seja responsável pelo design das operações para produtos de colaboração.</li><li>Defina os modelos de operação e suporte.</li><li>Contribuir com análises mensais e trimestrais para empresas.</li></ul>                                                                                                 | A ser determinado                                                  |
| Gerente de projetos               | <ul><li>Desenvolva e mantenha o plano do projeto.</li><li>Gerencie resultados finais do projeto em linha com o plano e o orçamento do projeto.</li><li>Registre e gerencie problemas de projeto, incluindo escalonamentos.</li><li>Realize chamadas standup semanais.</li><li>Liaise com e forneça atualizações para os patrocinadores executivos do projeto.</li><li>Trabalhe com equipes de comunicação e gerenciamento de alterações internas para atualizar a abordagem de gerenciamento de alterações e os planos de comunicação conforme necessário.</li></ul>                                                                                                                                                   | A ser determinado                                                  |
| Líder de rede                  | <ul><li>Forneça entradas no design de rede durante a fase de descoberta.</li><li>Participe do planejamento durante os workshops da fase do enVision.</li><li>Coordene o trabalho da equipe de rede durante a execução do projeto.</li></ul>                                                                                                                               | A ser determinado                                                  |
| Líder de segurança                 | <ul><li>Fornecer informações sobre o design de segurança e processos durante a fase de descoberta.</li><li>Participe do planejamento durante os workshops da fase do enVision.</li><li>Coordene o trabalho da equipe de segurança durante a execução do projeto.</li></ul>                                                                                                                | A ser determinado                                                  |
| Líder de telefonia                | <ul><li>Forneça a entrada no design de telefonia durante a fase de descoberta.</li><li>Participe do planejamento durante os workshops da fase do enVision.</li><li>Coordene o trabalho da equipe de telefonia durante a execução do projeto.</li></ul>                                                                                                                           | A ser determinado                                                  |
| Líder de desktop                  | <ul><li>Forneça a entrada de clientes e o processo de atualização durante a fase de descoberta.</li><li>Participe do planejamento durante os workshops da fase do enVision.</li><li>Coordene o trabalho da equipe da área de trabalho durante a execução do projeto.</li></ul>                                                                                                              | A ser determinado                                                  |
| Representantes das unidades de negócios | <ul><li>Contribuir com guias e materiais de adoção baseados em usuário.</li><li>Contribuir para e analisar os casos de uso comercial.</li></ul>                                                                                                                                   | A ser determinado                                                  |
| Administradores de TI                     | <ul><li>Assistência com o planejamento e a execução de testes (esta função é para profissionais de ti).                                                                                                                       | A ser determinado                                                  |
| Proprietário do serviço                 | <ul><li>Seja responsável pela operação do sistema telefônico com serviço de planos de chamadas, tudo.</li><li>Servir como proprietário do sistema telefônico com o serviço de planos de chamadas.</li></ul>                                                                                                               | A ser determinado                                                  |
| Testar Lead/gerente             | <ul><li>Defina o plano de teste, incluindo atividades, dependências, ambiente, metas, estratégia, resourcing (ambiental e humano) e a linha do tempo necessária para dar suporte à fase de teste.</li><li>Coordene a entrega e a preparação para as dependências do plano de teste.</li><li>Alinhar-se com a prioridade certa para a resolução do defeito.</li><li>Serve como caminho de escalonamento para quaisquer problemas de teste que surjam.</li><li>Comunicar e relatar o status do plano de teste com equipes internas e participantes designados.</li><li>Documentar e apresentar resultados de teste finais.</li></ul> | A ser determinado                                                  |
| Sistema telefônico com testador de planos de chamada     | <ul><li>Revise o plano de teste para entender os requisitos de teste, as metas, a linha do tempo, a resolução de problemas e os casos de teste a serem executados.</li><li>Revisar e desenvolver casos de teste que dão suporte a sistema telefônico com requisitos de aceitação e funcionalidade de planos de chamada.</li><li>Executar casos de teste e os resultados do teste de documento.</li><li>Os documentos são resolvidos conforme eles surgem e escalonam-os ao líder do teste para priorização e resolução.</li><li>Teste as regressões para fechar defeitos após a confirmação da resolução do defeito.</li></ul>                                                                | A ser determinado                                                  |
| Testador de rede                | <ul><li>Revise o plano de teste para entender os requisitos de teste, as metas, a linha do tempo, a resolução de problemas e os casos de teste a serem executados.</li><li>Examine os casos de teste que dão suporte à aceitação de preparação de rede e aos requisitos de desempenho.</li><li>Executar testes relacionados à preparação da rede, incluindo conectividade de rede e validação de desempenho, validação de QoS e validação de configuração de túnel dividido.</li><li>Concluir a validação da largura de banda dos sites em escopo usando o Network Planner por meio do myadvisor.</li><li>Documentar resultados de testes de preparação de rede.</li><li>Os documentos são resolvidos conforme eles surgem e escalonam-os ao líder do teste para priorização e resolução.</li><li>Teste as regressões para fechar defeitos após a confirmação da resolução do defeito.</li></ul>                                                                | A ser determinado                                                  |
| Testador de segurança               | <ul><li>Revise o plano de teste para entender os requisitos de teste, as metas, a linha do tempo, a resolução de problemas e os casos de teste a serem executados.</li><li>Revise e desenvolva casos de teste que dão suporte a requisitos de aceitação de segurança.</li><li>Executar testes relacionados à aceitação de segurança para casos de teste.</li><li>Documentar resultados do teste de aceitação de segurança.</li><li>Os documentos são resolvidos conforme eles surgem e escalonam-os ao líder do teste para priorização e resolução.</li><li>Teste as regressões para fechar defeitos após a confirmação da resolução do defeito.</li></ul>                                                                | A ser determinado                                                  |
| Testador de telefonia              | <ul><li>Revise o plano de teste para entender os requisitos de teste, as metas, a linha do tempo, a resolução de problemas e os casos de teste a serem executados.</li><li>Revise os casos de teste que dão suporte ao número de serviço, aceitação e requisitos de funcionalidade.</li><li>Execute testes relacionados à portabilidade do número de serviço, incluindo a porta do número de serviço para o Office 365.</li><li>Executar casos de teste e fazer o documento dos resultados do caso de teste.</li><li>Os documentos são resolvidos conforme eles surgem e escalonam-os ao líder do teste para priorização e resolução.</li><li>Teste as regressões para fechar defeitos após a confirmação da resolução do defeito.</li></ul>                                                                | A ser determinado                                                  |
| Sistema telefônico com teste de administração de planos de chamada | <ul><li>Revise o plano de teste para entender os requisitos de teste, as metas, a linha do tempo, a resolução de problemas e os casos de teste a serem executados.</li><li>Revise e desenvolva casos de teste que dão suporte a sistemas de telefonia com planos de chamadas e requisitos de funcionalidade de aceitação.</li> <li>Executar casos de teste e fazer o documento dos resultados do caso de teste.</li><li>Os documentos são resolvidos conforme eles surgem e escalonam-os ao líder do teste para priorização e resolução.</li><li>Teste as regressões para fechar defeitos após a confirmação da resolução do defeito.</li></ul>                                                                | A ser determinado                                                  |


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Pontos de decisão</td><td><ul><li>Decida quais são as funções de suporte e de Stakeholder necessárias para testar o sistema telefônico com recursos de planos de chamada em seu ambiente.</li><li>Decida quais recursos você atribuirá para o suporte de teste e as funções de Stakeholder que você identificou.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Próximas etapas</td><td><ul><li>Documente as funções de suporte de teste e de Stakeholder necessárias na matriz de suporte de teste.</li><li>Informações de contato do documento e detalhes do local para cada recurso que você lista na matriz de participantes do suporte de teste.
</table>


<a name="define-phone-system-with-calling-plans-feature-requirements"></a>Definir requisitos de recursos do sistema telefônico com planos de chamada 
------------------------------------------------------------

Como parte da definição de recursos do sistema telefônico com planos de chamada para usuários no escopo, consulte [sistema telefônico com planos de chamada](calling-plan-landing-page.md).
Em seguida, avalie o roteiro público das equipes mais recentes para determinar:

-   Qual sistema telefônico tem recursos de planos de chamada que você irá implantar para os usuários no escopo.

-   Sistema de telefonia do usuário esperado com requisitos de funcionalidade de planos de chamada, considerando seu atual Skype for Business, Exchange e o cenário de implantação do SharePoint.

-   Se você pode confirmar que o sistema telefônico com planos de chamada recursos descritos no mapa público mais recente atenda aos requisitos de usuário, funcionalidade e escopo na linha do tempo da sua implantação

> [!TIP]
> O mapa mais recente das equipes para identificar o sistema telefônico com planos de chamada recursos no escopo para sua implantação <https://aka.ms/O365Roadmap>pode ser encontrado em.

Agora que o sistema telefônico com os planos de chamada persona e os recursos foram definidos, o próximo critério para avaliação será a experiência de interoperabilidade com o Teams. Para obter informações adicionais sobre a experiência de interoperabilidade juntamente com as opções de configuração disponíveis, consulte [Microsoft Teams e interoperabilidade do Skype for Business](https://docs.microsoft.com/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability).

#### <a name="phone-system-with-calling-plans-feature-definition"></a>Definição de recurso do sistema telefônico com planos de chamada

> [!TIP]
> Veja a seguir um exemplo de um sistema telefônico com o modelo de definição de planos de chamada que você pode usar para documentar o sistema telefônico com os recursos de administração e grupo de usuários e administração de planos de chamadas a serem avaliados.


| Em nível empresarial   | Reuniões colaborativas    | Plataforma e dispositivos   | Profissionais de ti  | Grupo de negócios adicional, específico do site  | Requisitos atendidos pelo mais recente roteiro da equipe |
|-------------------------------------------|----------------------------|------------------|------------------------|-------------------|-------------------|
| <ul><li>Recursos de chamada do sistema telefônico:<ul><li>Transferência oculta</li><li>Bloqueio de chamadas</li><li>Encaminhamento de chamadas</li><li>Mascaramento de identificação de chamadas</li><li>Suporte E911</li><li>Discagem de extensão</li><li>Chamada em espera</li><li>Manipulação de chamadas múltiplas</li><li>Toque simultâneo</li><li>Correio de voz do Azure</li></ul></li><li>Suporte ao plano de chamada</li></ul> |<ul><li>Chamadas do Skype para empresas a equipes</li></ul> |<ul><li> Suporte a recursos de reuniões do cliente do Windows, do Mac Teams</li><li>Suporte do recurso reuniões do cliente nas equipes do navegador para:<ul><li>Janelas</li><li>Microsoft Edge</li></ul></li><li>suporte do recurso reuniões do cliente das equipes do Android e iOS</li><li>Suporte a TTY</li></ul> | <ul><li>Portal de diagnóstico de qualidade da chamada</li><li>Plano de discagem do locatário</li><li>Políticas de identificação de chamadas de locatário</li><li>Habilitar a análise de qualidade da chamada (CQD)</li></ul> | <ul><li>Validar recursos de reunião do teams com base na imagem do laptop corporativo</li><li>Suporte a idioma específico</li><li>Configurações de GPO aplicadas a um determinado cenário de usuário ou a um site específico</li></ul> | Sim  |




#### <a name="phone-system-with-calling-plans-user-functionality-definition"></a>Sistema telefônico com definição de funcionalidade do usuário dos planos de chamada

> [!TIP]
> Veja a seguir um exemplo de um modelo de funcionalidade do usuário que você pode usar para documentar a experiência do usuário necessária com base no sistema telefônico com recursos de planos de chamada a serem avaliados.


| Experiência do Exchange                          | Experiência do SharePoint                            | Experiência da política de interoperabilidade de equipes |
|----------------------------------------------|--------------------------------------------------|------------------------------------------|
| <ul><li>Criar equipes (criação de grupo do Office habilitada)</li><li>Entrar em equipes</li><li>Criar canais</li><li>Criar e visualizar reuniões</li><li>Modificar fotos de perfil de usuário</li><li>Adicionar e configurar conectores</li><li>Adicionar e configurar guias</li><li>Adicionar e configurar bots</li></ul> | <ul><li>Armazenar e compartilhar arquivos em conversas da equipe</li><li>Armazenar e compartilhar e compartilhar arquivos em chats privados (com base no OneDrive)</li></ul> | <ul><li>ChatDefaultClient: padrão</li><li>CallingDefaultClient: padrão</li></ul>      |


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Pontos de decisão</td><td><ul><li> Decida qual sistema telefônico tem os recursos de categoria de planos de chamada que você implantará em seu ambiente.</li><li>Identifique o sistema de telefone do usuário com os requisitos de funcionalidade dos planos de chamadas, de acordo com o atual Skype for Business, Exchange e o cenário de implantação do SharePoint.</li><li>Decidir qual é a experiência de interoperabilidade do teams que você vai implantar.</li><li>Examine o roteiro público das equipes mais recentes e decida se as funcionalidades de carga de trabalho atuais atendem à linha do tempo de implantação.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Próximas etapas</td><td><ul><li>Documentar o sistema telefônico com planos de chamada recursos de categoria necessários para dar suporte ao seu sistema telefônico com a implantação de planos de chamada.</li><li>Documentar o sistema de usuários com planos de chamadas e requisitos de interoperabilidade fornecidos ao seu atual Skype for Business, Exchange e cenário de implantação do SharePoint.</li><li>Documente se o roteiro público das equipes mais recentes que representa o sistema telefônico com recursos de planos de chamada atende às necessidades comerciais e aos requisitos de tempo da sua implantação.</li></ul></td></tr>
</table>

<a name="define-and-document-your-phone-system-with-calling-plans-test-plan"></a>Definir e documentar o sistema telefônico com o plano de teste de planos de chamada
------------------------------------------------------------------

Depois de definir o sistema telefônico com recursos de planos de chamada no escopo, a próxima etapa é criar o plano de teste. Em um nível alto, o plano de teste abrange a estratégia geral de teste e a metodologia que você usará para dar suporte à validação de recursos no processo de teste.

Em um nível alto, o plano de teste deve incluir:

-   **Testando o escopo:** Resume as áreas de foco (objetivos, cenários e objetivos) a serem avaliadas como parte da fase de teste

-   **Casos de teste:** O conjunto de casos de teste a serem validados para o sistema telefônico com recursos de planos de chamada no escopo

-   **Testando recursos:** Uma matriz de recursos necessários para dar suporte ao esforço de teste de um ponto de vista ambiental, técnico e de pessoal

-   **Cronograma de testes (linha do tempo):** Representa quando o teste começará, por quanto tempo ele pode durar e quando você espera que a fase de teste termine

-   **Relatórios de defeito e correção:** Diretrizes sobre como os problemas com o teste devem ser reportados, rastreados e triantigos

-   **Triagem de defeito e escalonamento:** Estrutura de tópicos de como e quando um escalonamento de defeito deve ser iniciado

-   **Testando critérios de saída e suspensão:** Diretrizes descrevendo critérios para obter a aprovação para sair da fase de teste ou pausar testes até que os defeitos priorizados sejam resolvidos

-   **Teste de entregas:** Resumo de quais resultados serão desenvolvidos e entregues para dar suporte à aceitação da assinatura e saída do processo de teste

> [!TIP]
>   Uma metodologia de teste já pode existir em sua organização, mas a orientação abaixo reflete as práticas recomendadas que podem ser incluídas ou aproveitadas separadamente para testar os recursos da equipe em seu ambiente.

Nas seções a seguir, você encontrará orientação adicional prescrita que dará assistência a decisões específicas, modelos e tópicos para você considerar ao concluir o plano de testes.

### <a name="define-and-document-testing-scope"></a>Definir e documentar o escopo do teste

Ao trabalhar para desenvolver seu plano de teste, você deve definir o escopo de teste antecipado, realçando a carga de trabalho e a lista de recursos que você está avaliando.

O escopo para a avaliação adequada do sistema telefônico com planos de chamada recursos inclui normalmente:

-   Sistema telefônico com planos de chamada preparação do site

-   Sistema telefônico com experiência do usuário em planos de chamada

-   Sistema telefônico com administração de planos de chamada

#### <a name="phone-system-with-calling-plans-testing-scope"></a>Sistema telefônico com planos de chamadas de teste

> [!TIP]
>   Veja a seguir um exemplo de modelo de escopo de teste que você pode usar para documentar o sistema telefônico com a administração de planos de chamadas e os recursos de grupo de usuários a serem avaliados.

| Sistema telefônico com planos de chamada preparação do site                                                                                                                                                                                    | Sistema telefônico com experiência do usuário em planos de chamada                                                                                                                                                                                         | Sistema telefônico com experiência de administração de planos de chamada                                                                           |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| <ul><li>Planejamento de largura de banda do Planner de rede (por meio do myadvisor)<li></li>Conectividade de rede e validação de desempenho (por meio da ferramenta de avaliação de rede do Skype for Business)<li></li>Validação da qualidade do serviço (QoS)<li></li>Validação de túnel dividido de acesso remoto</li></ul>|<ul><li>Recursos de PBX<li></li>Chamada PSTN (doméstica e internacional)<li></li> Colocar e receber chamadas PSTN<li></li>Correio de voz do Azure<li></li>E911<li></li>Plano de discagem do locatário<li></li>Mascaramento de ID de chamadas de locatário <li></li>Recursos avançados de controle de chamada (por exemplo, encaminhamento de chamadas, toque simultâneo)</li></ul> |<ul><li>Atribuição de licenciamento</li><li>Portador de número do assinante para o Office 365</li><li>Sistema telefônico com relatórios de planos de chamada</li><li>Relatório de qualidade de chamada (CQD)</li></ul> |

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Pontos de decisão</td><td><ul><li>Decida qual o sistema telefônico com planos de chamadas para testar o escopo ao identificar os recursos a serem avaliados pela área de foco.</li><li>Decidir metas e objetivos adicionais para avaliação.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Próximas etapas</td><td><ul><li>Documentar o sistema telefônico com recursos de planos de chamada a serem avaliados pela área de foco.</li><li>Documentar metas adicionais e objetivos para avaliação.</li></ul></td></tr>
</table>

### <a name="define-and-document-phone-system-with-calling-plans-test-cases"></a>Definir e documentar o sistema telefônico com casos de teste de planos de chamada

Depois de definir o sistema telefônico com planos de chamada, recursos de implantação e implantação do cliente e cenários lado a lado com o Skype for Business (se aplicável), a próxima etapa é formular os casos de teste necessários para avaliar o sistema telefônico com recursos de planos de chamada no com. Em um nível alto, os casos de teste geralmente são agrupados por área de foco e incluem:

-   **Título do caso de teste:** Área de foco do recurso o teste está avaliando (por exemplo, sistema telefônico com planos de chamada)

-   **Descrição do caso de teste:** Resumo descrevendo as metas dos recursos de teste sendo avaliados

-   **Instruções do caso de teste:** Etapas a serem seguidas para executar corretamente o caso de teste sendo executado

-   **Ambiente obrigatório (pré-requisitos):** Instruções de configuração necessárias para executar corretamente o teste

-   **Recurso obrigatório:** Recursos de pessoal necessários para avaliação e execução adequadas do teste

-   **Resultados esperados:** O resultado esperado após o teste ser concluído com êxito

> [!NOTE]
>   Como a abordagem e o nível de detalhes necessários para a criação de casos de teste podem variar de acordo com a sua organização, é uma boa ideia seguir uma abordagem que permita um nível adequado de detalhes, mas o equilíbrio da abrangência à praticidade, para dar suporte a testes gerais gerenciamento.

> [!TIP]
>   Para ajudar a criação de casos de teste como ponto de partida, confira a lista de diretrizes do usuário do sistema telefônico disponível em [reuniões e chamadas](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8)do Microsoft Teams.

#### <a name="phone-system-with-calling-plans-test-case"></a>Sistema telefônico com caso de teste de planos de chamada

> [!TIP]
>   Veja a seguir um exemplo de modelo de caso de teste que você pode usar para documentar o sistema telefônico com a administração de planos de chamadas e os recursos de grupo de usuários a serem avaliados.

Sistema telefônico com validação de planos de chamada

| ID do caso de teste | Título do caso de teste               | Descrição do caso de teste                                                  | Ambiente necessário para execução do caso de teste                                               | Etapas necessárias para execução do caso de teste                                                                                                                                                          | Recursos de teste obrigatórios              |
|--------------|-------------------------------|------------------------------------------------------------------------|--------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------|
| 1            | Como colocar uma chamada PSTN de saída | Verifique se você pode fazer uma chamada de voz externa para um número de 10 dígitos. |<ul><li>Cliente do Microsoft Teams instalado.</li><li>Usuário habilitado com as seguintes licenças do Office 365 atribuídas:<ul><li>Office Enterprise E5 com sistema telefônico, Microsoft Teams e planos de chamadas locais e internacionais</li><li>Office Enterprise E3 com sistema telefônico, Microsoft Teams e planos de chamadas locais e internacionais</li></ul></li></ul> | <ol><li>Entre no cliente do teams.</li><li>Selecione o teclado de discagem e digite um número de 10 dígitos para discar.</li><li>Verifique se a discagem de número está corretamente normalizada e se a chamada PSTN externa foi estabelecida.</li></ol>    | Sistema telefônico com testador de planos de chamada |


> [!TIP]
>   Para obter orientação adicional para facilitar o caso de teste individual e a criação do plano geral para avaliar o sistema telefônico com recursos de planos de chamada em sua organização, examine o [plano de teste do sistema de telefonia](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_21) fornecido pelo myadvisor. [](https://myadvisor.fasttrack.microsoft.com/)


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Pontos de decisão</td><td><ul><li>Decida qual sistema telefônico com a administração de planos de chamadas e os recursos de usuário serão avaliados.</li><li>Decida qual ambiente de teste é necessário para dar suporte à execução de casos de teste.</li><li>Decida quais etapas são necessárias para a avaliação de caso de teste.</li><li>Decida os recursos necessários para a execução adequada do teste.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Próximas etapas</td><td><ul><li>Documentar os casos de teste a serem avaliados com base no modelo de caso de teste fornecido.</li><li>Inclua o modelo concluído como parte do seu plano de teste geral.</li></ul></td></tr>
</table>


### <a name="define-and-document-testing-resources"></a>Definir e documentar recursos de teste

Para dar suporte à fase de teste, é importante que você desenvolva um plano de recursos detalhando as pessoas, o suporte e os recursos de tecnologia que precisará. Um componente importante do plano de teste geral, o plano de recursos ajuda você a determinar as dependências que podem existir e oferece a você um sentido de alto nível do suporte a recursos que talvez seja necessário.

Em um nível alto, esses recursos geralmente consistem em:

-   **Pessoas**: participantes

-   **Tecnologia**: locatário, licenciamento, dispositivos

-   **Suporte**: treinamento (cartões, vídeos), suporte de administração com caminho de escalonamento definido

#### <a name="testing-resource-requirements"></a>Testando requisitos de recursos

> [!TIP]
>   Veja a seguir um exemplo de como testar o modelo de requisito de recurso que você pode usar para documentar os diferentes tipos de recursos necessários para dar suporte à fase de teste.


| Tipo de recurso | Recursos necessários                                           | Descrição do recurso |
|---------------|--------------------------------------------------------------|----------------------|
| Pessoas        | Os stakeholders testam os testadores de Lead                               | A ser determinado                  |
| Tecnologia    | Acesso ao Office 365 com os seguintes serviços habilitados:<ul><li>Licenciamento do Office 365 E5 atribuído</li><li>Plano de chamadas domésticas e internacionais atribuído</li></ul>    | A ser determinado                  |
| Suporte       | Testar o responsável pelo suporte teste do administrador Lead Technician | A ser determinado                  |

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Pontos de decisão</td><td><ul><li>Decida quais tipos de recursos (pessoas, tecnologia e suporte) você precisará dar suporte à fase de teste.</li><li>Decida quais recursos específicos são necessários para os tipos de recursos que você identificou.</li><li>Decida se você deve fornecer mais detalhes para descrever os tipos de recursos de que você precisa.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Próximas etapas</td><td><ul><li>Documente os tipos de recursos (pessoas, tecnologia e suporte) que você precisará dar suporte à fase de teste.</li><li>Documente os recursos específicos necessários para os tipos de recursos que você identificou.</li><li>Se você decidir que é necessário, documente mais detalhes sobre os tipos de recursos necessários para dar suporte à fase de teste.</li></ul></td></tr>
</table>


### <a name="define-and-document-a-testing-timeline"></a>Definir e documentar uma linha do tempo de teste

Como parte da definição do plano de teste, crie uma linha do tempo que descreve o cronograma para quando você espera concluir atividades de teste e obter Marcos de alto nível.

Em um nível alto, isso normalmente consiste em:

-   **Tarefa:** Atividade de alto nível a ser concluída

-   **Marco:** Objetivo de alto nível ou progresso concluído

-   **Recurso obrigatório:** Testes de recursos necessários para dar suporte à entrega da etapa ou tarefa identificada

-   **Data de início:** A data em que a atividade, Marco ou tarefa foi iniciada

-   **Data de conclusão:** A data em que você espera que a atividade, etapa do trabalho ou tarefa seja concluída por

-   **Proprietário:** Recurso atribuído que é responsável por assegurar que a atividade, Marco ou tarefa seja concluída no tempo, de acordo com a data de conclusão

-   **Previsão:** Número de horas que os recursos atribuídos anteciparão para garantir que a atividade, Marco ou tarefa seja concluída no prazo

#### <a name="testing-scheduling-and-timeline-requirements"></a>Testar requisitos de agendamento e linha do tempo

> [!TIP]
>   Veja a seguir um exemplo de um modelo de requisito de linha do tempo de teste que você pode usar para documentar as datas previstas quando atividades específicas de teste serão concluídas ou marcos entregues pela.

| Tarefa                                                 | Tina       | Data de início                                                             | Data de conclusão | Proprietário | Recursos atribuídos | Estimativa |
|------------------------------------------------------|-----------------|------------------------------------------------------------------------|-----------------|-------|--------------------|------------|
| Relatório de teste                                          | A ser determinado             | A ser determinado                                                                    | A ser determinado             | A ser determinado   | A ser determinado                | A TBD horas  |
| Execução do caso de teste: sistema telefônico com planos de chamada | A ser determinado             | A ser determinado                                                                    | A ser determinado             | A ser determinado   | A ser determinado                | A TBD horas  |
| Execução do caso de teste: preparação da rede               | A ser determinado             | A ser determinado                                                                    | A ser determinado             | A ser determinado   | A ser determinado                | A TBD horas  |


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Pontos de decisão</td><td><ul><li>Escolha atividade da linha do tempo, etapa do tempo e tarefas que você precisa acompanhar.</li><li>Decida quais recursos você precisará atribuir.</li><li>Escolha a data que você espera que seja concluída.</li><li>Identifique o proprietário da entrega.</li><li>Decida quanto tempo levará para concluir a atividade, Marco ou tarefa.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Próximas etapas</td><td><ul><li>Documente a linha do tempo de teste usando o modelo fornecido e inclua:<ul><li>Atividade da linha do tempo, etapa do tempo e tarefas que precisam ser rastreadas.</li><li>Recursos que precisam ser atribuídos.</li><li>Data de conclusão prevista.</li><li>Proprietário da entrega.</li><li>Tempo necessário para concluir a atividade, Marco ou tarefa.</li></ul></li><li>Inclua o modelo concluído como parte do seu plano de teste geral.</li></ul></td></tr>
</table>


### <a name="define-and-document-test-defect-report-criteria"></a>Definir e documentar critérios de relatório de falha de teste

Como casos de teste dentro de uma determinada fase ou fluxo são executados, podem surgir problemas onde o resultado do caso de teste sendo executado não é o que você esperava.

Quando esses tipos de resultados ocorrem, eles devem ser capturados em um relatório de defeito e plano de correção que é escalonado para o cliente potencial designado para revisão, relatório e resolução de defeito.

Geralmente, um relatório de defeito e um plano de correção incluem o seguinte:

-   **Identificação do defeito:** O número atribuído ao problema

-   **ID do caso de teste afetado**: o número atribuído ao caso de teste que estava sendo avaliado no momento em que o defeito foi identificado

-   **Descrição do defeito:** Resumo do problema

-   **Ambiente/etapas para reproduzir:** Resumo da configuração do ambiente de teste, juntamente com as etapas exatas necessárias para reproduzir o problema

-   **Severidade do defeito**: o impacto do problema, desde impedir que o caso de teste seja aprovado para ser aceito com risco mínimo. Alguns exemplos podem incluir:

-   **Baixo:** O problema tem pouco impacto e não impedirá que o caso de teste seja aceito se o problema puder ser resolvido mais tarde.

-   **Média:** O problema tem um impacto significativo, mas não impede que o caso de teste seja aceito se o problema puder ser resolvido antes da conclusão da fase de teste.

-   **Alta:** -o problema tem impacto crítico no caso de teste. O problema deve ser resolvido antes que o caso de teste possa ser aceito.

-   **Status:** O problema foi resolvido, está aberto ou ainda em investigação

-   **Enviado por:** O testador que relatou o problema

-   **Proprietário atribuído:** O recurso atribuído pela equipe de teste responsável pela resolução do problema

-   **Detalhes de suporte:** Isso pode incluir, mas não se limitando a, registros do lado do cliente, capturas de tela ou vídeo sobre o problema.

Como os testadores executam os casos de teste descritos em seu plano de teste, eles devem ter certeza de concluir um relatório de falha e um plano de correção para quaisquer problemas que surgirem.
Isso realçará o impacto potencial que pode impedir ou mesmo interromper o processo de avaliação de teste.

#### <a name="testing-defect-report-and-remediation-plan"></a>Testando relatório de defeito e plano de correção

> [!TIP]
>   Veja a seguir um exemplo de relatório de defeitos e modelo de plano de correção que você pode usar para documentar os problemas descobertos durante a fase de teste.

| ID do defeito                                | ID do caso de teste afetada | Descrição do defeito                                                                                 | /Steps de ambiente para reprodução                                                                                                | Gravidade | Situação | Enviado por | Proprietário atribuído | Detalhes de suporte (registros, capturas de tela e assim por diante) |
|------------------------------------------|-----------------------|----------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------|----------|--------|--------------|----------------|---------------------------------------------------|
| 1                                        | 1                     | Quando o usuário insere uma extensão de quatro dígitos, tentando fazer uma chamada de saída, a chamada falha. | No cliente do Teams, selecione o teclado de discagem, insira uma extensão de quatro dígitos e selecione o ícone de telefone para tentar fazer a chamada. | Média   | Fechado | Lahr de Louis   | Lisa em cinza      | Log do lado do cliente das equipes<br/> Captura de tela do cliente do teams     |


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Pontos de decisão</td><td><ul><li>Decida quais níveis de severidade de critérios de defeito você atribuirá para dar suporte ao esforço de teste.</li><li>Decida o que testa critérios de relatório de falhas você documentará se os problemas surgirem durante o teste.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Próximas etapas</td><td><ul><li>Documentar os critérios de relatório de falha de teste necessários no modelo fornecido.</li><li>Inclua o modelo concluído como parte do seu plano de teste geral.</li></ul></td></tr>
</table>


### <a name="define-and-document-exit-and-suspension-criteria"></a>Definir e critérios de saída e suspensão do documento

Como parte do processo geral de execução do plano de teste, você precisa definir critérios para indicar o ponto no qual deve suspender os esforços de teste versus requisitos que devem ser atendidos para obter a aprovação e sair da fase de teste.

#### <a name="test-plan-exit-and-suspension-criteria"></a>Critérios de saída do plano de teste e suspensão

> [!TIP]
>   Veja a seguir um exemplo de modelo de critérios de saída e saída que você pode usar em seu plano de teste para documentar os critérios necessários para obter a aprovação, sair da fase de teste ou suspender atividades de teste.

| Testando critérios de saída                            | Testar critérios de suspensão                      |
|--------------------------------------------------|--------------------------------------------------|
|<ul><li>Todos os casos de teste devem obter uma taxa de aprovação de TBD%</li><li>Todos os casos de teste devem ter sido completamente executados</li><li>Em todos os casos de teste avaliados, todos os defeitos de alta gravidade devem ser fechados</li></ul> | <ul><li>Todos os casos de teste devem obter uma taxa de falha de TBD%</li><li>Todos os defeitos identificados como alta gravidade devem ser resolvidos antes que o teste possa continuar.</li></ul> |


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Pontos de decisão</td><td><ul><li>Escolha os critérios de suspensão que devem ser atendidos se problemas com o teste forem identificados.</li><li>Escolha os critérios de saída que devem ser atendidos para obter a aprovação de teste de aceitação e suporte à saída da fase de teste após a conclusão de todas as atividades de teste.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Próximas etapas</td><td><ul><li>Documente os critérios de saída de teste e de suspensão necessários nos modelos Test e Exit fornecidos.</li></ul></td></tr>
</table>


### <a name="define-and-document-the-defect-escalation-process"></a>Definir e documentar o processo de escalonamento de defeito

Durante o curso de execução do plano de teste, você pode descobrir um problema ou identificar um defeito que exige escalonamento para o recurso certo para direcionar e determinar a resolução necessária para permitir que o teste continue.

Quando os defeitos são identificados com a gravidade e a prioridade adequadas atribuídas, você cria uma matriz de escalonamento e um processo de revisão de triagem para mapear quando um escalonamento é disparado e como, quando e para quem o defeito será atribuído para revisão adicional e nomes.

Geralmente, um relatório de defeito e um plano de correção incluem o seguinte:

-   **Identificação do defeito:** O número atribuído ao problema

-   **Descrição do defeito:** Resumo do problema

-   **Avaliação de prioridade de defeito:** O nível de prioridade atribuído a um defeito para a resolução com base no impacto no negócio e na severidade do defeito. Alguns exemplos podem incluir:

-   **Baixo:** O problema tem pouco impacto para impedir que a fase de teste atinja a aprovação se o problema puder ser resolvido mais tarde.

-   **Média:** O problema tem um impacto significativo na prevenção da fase de teste para obter a aprovação caso o problema não possa ser resolvido.

-   **Alta:** O problema tem impacto crítico para impedir que a fase de teste atinja a aprovação se o problema não puder ser resolvido.

-   **Proprietário do defeito atribuído:** O recurso atribuído pela equipe de teste responsável por resolvê-lo

-   **Ponto de escalonamento do defeito atribuído:** O recurso atribuído que está no ponto de encaminhar o problema na organização (se necessário) para obter a resolução de problemas; com base na severidade do defeito

-   **Status do defeito:** O problema foi resolvido, está aberto ou ainda em investigação

-   **Resolução necessária por data:** A data em que o problema deve ser resolvido por

-   **Data do status:** A data que reflete o último tempo em que o status foi atualizado como resultado de uma análise de triagem de defeito

#### <a name="test-plan-defect-escalation"></a>Escalonamento do defeito do plano de teste

> [!TIP]
>   Veja a seguir um exemplo de um modelo de escalonamento de defeito que você pode usar em parte do seu plano de teste para documentar o processo de escalonamento necessário para priorizar e solucionar problemas de teste.

| ID do defeito                                | Descrição do defeito                                                                                 | Avaliação de prioridade de defeito                                           | Proprietário do defeito atribuído | Ponto de escalonamento do defeito atribuído | Método de escalonamento de defeito                                          | Status do defeito | Resolução necessária por data | Data de status |
|------------------------------------------|----------------------------------------------------------------------------------------------------|----------------------------------------------------------------------|-----------------------|----------------------------------|-------------------------------------------------------------------|---------------|-----------------------------|-------------|
| 1                                        | Quando o usuário insere uma extensão de quatro dígitos, tentando fazer uma chamada de saída, a chamada falha. | Média                                                               | Lisa em cinza             | Lahr de Louis                       | Triagem semanal revisar email de alta prioridade para stakeholders afetados | Abriu          | URGENTE                        | 1/12/2018   |



<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Pontos de decisão</td><td><ul><li>Decida e concorde com as prioridades do defeito para dar suporte ao seu plano de teste.</li><li>Escolha o ponto de escalonamento para cada área de defeito.</li><li>Decida o plano de falha e o plano de triagem para acompanhar, com base na prioridade.</li><li>Escolha o relatório de falhas e o plano de comunicação de triagem para escalonamento.</li><li>Decida qual a cadência da reunião examine a análise de defeito.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Próximas etapas</td><td><ul><li>Documente as prioridades acordadas do defeito.</li><li>Documentar o ponto de escalonamento para cada área de foco potencial.</li><li>Documentar o escalonamento do defeito e o plano de triagem com base nos critérios acordados.</li><li>Documentar as diretrizes de relatório de defeito.</li><li>Agende a série de reuniões de triagem de defeito.</li></ul></td></tr>
</table>


### <a name="define-and-document-testing-deliverables"></a>Definir e documentar os resultados do teste

O último e último componente da criação de um plano de teste é identificar os resultados em termos de resultados específicos que o plano de teste geral oferecerá.

Em um nível alto, eles normalmente incluem, mas não se limitam a:

-   Plano de teste

-   Casos de teste

-   Relatórios de defeito

-   Resumo dos resultados dos testes

-   Aceitação e aprovação de teste

#### <a name="test-plan-deliverables"></a>Testar resultados do plano

> [!TIP]
>   Veja a seguir um exemplo de matriz de entrega de um plano de teste que você pode usar para documentar os resultados finais a serem criados, juntamente com os recursos necessários para revisão, aprovação e aprovação.

| Entrega do plano de teste                    | Formato de entrega do plano de teste | Proprietário da entrega do plano de teste                                                                                                      | Revisor da entrega do plano de teste | Aprovador do resultado do plano de teste | Data de aprovação da entrega do plano de teste |
|------------------------------------------|------------------------------|----------------------------------------------------------------------------------------------------------------------------------|--------------------------------|--------------------------------|-------------------------------------|
| Plano de teste                                | Palavra                         | A ser determinado                                                                                                                              | A ser determinado                            | A ser determinado                            | A ser determinado                                 |
| Relatórios de gerenciamento de falhas                | Palavra                         | A ser determinado                                                                                                                              | A ser determinado                            | A ser determinado                            | A ser determinado                                 |
| Testando relatórios de status                   | Palavra                         | A ser determinado                                                                                                                              | A ser determinado                            | A ser determinado                            | A ser determinado                                 |
| Resumo dos resultados dos testes                     | Palavra PPTX                    | A ser determinado                                                                                                                              | A ser determinado                            | A ser determinado                            | A ser determinado                                 |


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Pontos de decisão</td><td><ul><li>Decida quais resultados serão criados e capturados como resultado de cada fase de teste. Para cada produto, decida em:<ul><li>Format</li><li>Proprietário</li><li>Revisor</li><li>Aprovador</li></ul></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Próximas etapas</td><td><ul><li>Documentar uma matriz de criação e entrega de um plano de teste.</li></ul></td></tr>
</table>


<a name="evaluate-network-readiness"></a>Avaliar a preparação da rede
----------------------------

Como um elemento crítico que dá suporte à implantação de suas equipes, a preparação de rede é uma parte crucial do teste para garantir que a rede esteja devidamente otimizada para dar suporte a comunicações de equipe. Para garantir que sua rede esteja pronta para os sites no escopo, inclua as áreas de foco listadas abaixo na estratégia geral de teste:

-   Planejamento e estimativa da largura de banda com o planejador de rede (por meio do myadvisor)

-   Validação da configuração de qualidade do serviço (QoS)

-   Conectividade de rede e desempenho verificando a simulação de tráfego

-   Validação do tunelamento de divisão

### <a name="execute-network-planner-through-myadvisor-for-sites-and-personas-in-scope"></a>Executar o planejador de rede (por meio do myadvisor) para sites e pessoas em escopo

Antes de apresentar serviços de comunicação em tempo real como equipes em seu ambiente, é importante garantir que a rede tenha sido corretamente otimizada e dimensionada de uma perspectiva do Azure ExpressRoute (se aplicável), da Internet e da largura de banda de WAN.

Para ajudar a determinar a quantidade de largura de banda e o nível de otimização da rede necessários para sites em escopo que dão suporte à sua implantação, conclua a ferramenta planejador de [rede](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner/Help?sectionName=DashboardHelp) (por meio do myadvisor) para validar as necessidades de preparação da rede da sua organização. Para obter diretrizes adicionais sobre como determinar os requisitos de rede do teams por meio do planejador de rede, consulte myadvisor: planejador de rede.

> [!TIP]
>   Para obter informações adicionais sobre a guia **recomendações** , com exemplos de como configurar e interpretar os resultados, consulte a [visão geral de recomendações](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner/Help?sectionName=RecommendationHelp)do planejador de rede.



<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/><br/>Pontos de decisão</td><td><ul><li>Decidir quais sites de rede estão no escopo para a implantação de serviços do teams.</li><li>Escolha as pessoas necessárias para as modalidades de equipe no escopo.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Próximas etapas</td><td><ul><li>Conclua o planejador de rede (por meio do myadvisor) para obter a lista de sites que estão no escopo.</li><li>Documentar resultados de validação do planejador de rede no modelo de resultados do plano de teste fornecido.</li><li>Valide se a largura de banda do ExpressRoute (se aplicável), da Internet e da WAN que foi calculada para sites no escopo se alinha aos valores de largura de banda que estão atualmente alocados.</li><li>Para sites que não têm largura de banda adequada, execute planos de escalonamento e correção para resolver problemas de largura de banda.</li><li>Estabeleça uma solução de monitoramento de rede para sites no escopo para monitorar o uso de largura de banda e a QoS para o ExpressRoute (se aplicável), Internet e segmentos WAN.</li><li>Programe uma reunião de Comitê de direcionamento para analisar os resultados do planejador de rede.</li><li>Apresente os resultados do planejamento de largura de banda ao Comitê de direcionamento para identificar qualquer área que exija remediação.</li></ul></td></tr>
</table>


<a name="evaluate-qos-configuration-for-sites-in-scope"></a>Avaliar a configuração de QoS para sites no escopo
---------------------------------------------

Como parte da validação da prontidão da rede para dar suporte às comunicações em tempo real do Teams, é igualmente importante garantir que a rede tenha sido corretamente configurada e otimizada de acordo com uma perspectiva de QoS.

Para obter diretrizes adicionais sobre como configurar, implantar e validar a preparação da rede QoS para o Microsoft Teams usando a política de grupo, consulte Habilitando o [QoS para Teams](https://docs.microsoft.com/MicrosoftTeams/qos-in-teams).


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/><br/>Pontos de decisão</td><td><ul><li>Decidir sobre a configuração de QoS a ser implementada.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Próximas etapas</td><td><ul><li>Configurar a QoS.</li><li>Execute a validação de QoS conforme descrito nas etapas listadas por meio das seções "validar via GPO" e "validar via Message Analyzer" acima.</li></ul></td></tr>
</table>


### <a name="document-qos-configuration-validation-test-results"></a>Resultados do teste de validação de configuração de QoS de documento

Depois de concluir o teste de validação de QoS usando a política de grupo para sites no escopo, crie um relatório que resuma os resultados do teste para apresentar durante a revisão do Comitê de direcionamento final.

#### <a name="site-a-qos-configuration-validation-testing-summary-report"></a>Site A: relatório de Resumo de teste de validação de configuração de QoS

> [!TIP]
>   Veja a seguir um exemplo de modelo de relatório de Resumo de teste que você pode examinar durante a próxima reunião do Comitê de direcionamento quando estiver decidindo quando você está decidindo quando o sistema telefônico onboard tem serviços de planos de chamada na fase piloto.


**Validação de configuração de QoS via GPO e analisador de mensagens**

**Resumo dos resultados**&nbsp; &nbsp; &nbsp; :&#9744;&nbsp; &nbsp; &nbsp; passar &#9744;&nbsp; &nbsp; parcial&nbsp; &#9744;falha

<table>
<tr><th colspan="2">Destaques do teste </th></tr>
<tr><td>A ser determinado</td><td>A ser determinado</td></tr>
<tr><th colspan="2">Testando lowlights  </th></tr><br/><tr><td><strong>Problema</strong>: TBD</td><td><strong>Correção:</strong> A ser determinado</td></tr>
<tr><th colspan="2">Bloqueadores identificados </td></tr>
<tr><td><strong>Bloqueador</strong>: TBD</td><td><strong>Correção</strong>: TBD</td></tr>
</table>


> [!TIP]
> Para facilitar mais discussão durante a revisão do Comitê de direcionamento final, você pode usar a [matriz de resultados de teste](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_21) atualizadas do myadvisor para documentar e destacar áreas adicionais que exijam correção. [](https://myadvisor.fasttrack.microsoft.com/)



<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/><br/>Pontos de decisão</td><td><ul><li>Avaliar os resultados do teste de QoS para garantir que o tráfego de mídia em tempo real do teams seja corretamente marcado e priorizado.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Próximas etapas</td><td><ul><li>Resultados do teste de QoS de documento no modelo de resultado do plano de teste fornecido.</li><li>Execute planos de escalonamento e correção para resolver problemas nos quais a QoS pode não estar devidamente configurada ou não está funcionando conforme esperado para dar suporte ao tráfego de mídia de equipes.</li></ul></td></tr><li>Agende uma reunião de Comitê de direção para revisar os resultados do resumo do teste.</li><li>Apresente os resultados do resumo do teste ao Comitê de direcionamento para identificar qualquer área que exija remediação.</li>
</table>


<a name="execute-split-tunnel-enablement-validation"></a>Executar a validação de habilitação de encapsulamento de divisão
------------------------------------------

Hoje, é comum que as empresas tenham uma ou mais soluções para fornecer acesso remoto, como uma rede virtual privada ou VPN. Essas soluções permitem a conectividade com ativos e aplicativos de linha de negócios internos com segurança e confiança.

Embora as soluções de acesso remoto possam funcionar muito bem para dar acesso a alguns aplicativos, quando se trata de encapsular o tráfego de mídia em tempo real das equipes em tempo real, essas soluções freqüentemente resultam em uma experiência do usuário inferior à ideal para todos os participantes em um áudio de equipe Conferência ou cenário de chamada.

Para garantir que o tráfego de mídia de equipe *não* percorra soluções de acesso remoto em seu ambiente, uma configuração de túnel dividido será necessária.

Para obter diretrizes adicionais sobre como configurar e validar a preparação da rede de configuração de Split-Tunnel para Teams, consulte preparação para a [rede](https://docs.microsoft.com/MicrosoftTeams/prepare-network) .

> [!NOTE]
>   Devido ao volume simples de soluções de acesso remoto disponíveis no mercado, este documento não pode fornecer detalhes específicos do fornecedor, apenas diretrizes gerais sobre o que deve ser configurado em soluções de acesso remoto.


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/><br/>Pontos de decisão</td><td><ul><li>Escolha a configuração de túnel de divisão a ser implementada.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Próximas etapas</td><td><ul><li>Implementar a configuração de túnel dividido.</li><li>Teste e valide a configuração de túnel dividido.</li></ul></td></tr>
</table>


### <a name="document-split-tunnel-configuration-validation-test-results"></a>Resultados do teste de validação de configuração de túnel de divisão de documento

Depois de concluir o teste da configuração de túnel dividido para sites no escopo, crie um relatório que resuma os resultados do teste e apresente-o durante a próxima revisão do Comitê de direção.

#### <a name="site-a-split-tunnel-configuration-validation-testing-summary-report"></a>Site A: relatório de Resumo de teste de validação de configuração de encapsulamento Split

> [!TIP]
>   Veja a seguir um exemplo de modelo de relatório de Resumo de teste que você pode examinar durante a próxima reunião do Comitê de direcionamento quando estiver decidindo quando você está decidindo quando o sistema telefônico onboard tem serviços de planos de chamada na fase piloto.

**Validação de configuração de túnel dividido**

**Resumo dos resultados**&nbsp; &nbsp; &nbsp; :&#9744;&nbsp; &nbsp; &nbsp; passar &#9744;&nbsp; &nbsp; parcial&nbsp; &#9744;falha

<table>
<tr><th colspan="2">Destaques do teste </th></tr>
<tr><td>A ser determinado</td><td>A ser determinado</td></tr>
<tr><th colspan="2">Testando lowlights  </th></tr><br/><tr><td><strong>Problema</strong>: TBD</td><td><strong>Correção:</strong> A ser determinado</td></tr>
<tr><th colspan="2">Bloqueadores identificados </td></tr>
<tr><td><strong>Bloqueador</strong>: TBD</td><td><strong>Correção</strong>: TBD</td></tr>
</table>


> [!TIP]
> Para facilitar mais discussão durante a revisão do Comitê de direcionamento final, você pode usar a [matriz de resultados de teste](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_21) atualizadas do myadvisor para documentar e destacar áreas adicionais que exijam correção. [](https://myadvisor.fasttrack.microsoft.com/)


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/><br/>Pontos de decisão</td><td><ul><li>Avalie os resultados dos testes de encapsulamento divididos para garantir que o tráfego em tempo real das equipes seja excluído da solução de acesso remoto.</li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Próximas etapas</td><td><ul><li>Os resultados do teste de conectividade do túnel de divisão de documentos no modelo de resultado do plano de teste fornecido.</li><li>Execute planos de escalonamento e correção para resolver problemas em que o roteamento adequado pode não existir para dar suporte à mídia de equipes em uma configuração de túnel dividido.</li><li>Agende uma reunião de Comitê de direção para revisar os resultados do resumo do teste.</li><li>Apresente os resultados do resumo do teste ao Comitê de direcionamento para identificar qualquer área que exija remediação.</li></ul></td></tr>
</table>


<a name="execute-network-connectivity-and-performance-validation-by-using-the-network-assessment-tool-from-microsoft"></a>Executar a conectividade de rede e a validação de desempenho usando a ferramenta de avaliação de rede da Microsoft
-----------------------------------------------------------------------------------------------------------

A ferramenta de avaliação de rede da Microsoft executa testes de conectividade e simulação de tráfego por meio do streaming de pacotes de áudio simulados, por um período e número de iterações predefinidos, para o site de borda mais próximo que fornece conectividade com o serviço Teams. Uma meta deste teste é avaliar as métricas de desempenho de rede para perda de pacotes, tremulação, latência de ida e volta e porcentagem de reordenação de pacotes de cada chamada simulada. Além disso, o teste valida se a conectividade adequada é permitida entre elementos de rede interna e de borda em todos os pontos de ingresso de borda que dão suporte à conectividade com os serviços do teams.

Para obter orientação adicional sobre como confirmar e avaliar a preparação da rede das equipes para sites designados em escopo, consulte preparação para a [rede](https://docs.microsoft.com/MicrosoftTeams/prepare-network) .

> [!TIP]
>   Para concluir a análise de preparação de rede e a preparação para os sites em escopo, designe um cliente potencial para cada site que possa ajudá-lo com seus esforços de avaliação de preparação de rede.



<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/><br/>Pontos de decisão</td><td><ul><li>Escolha o perfil de teste de conectividade e avaliação de rede para sites no escopo.</li><li>Escolha os requisitos de arquivo de configuração da avaliação de rede para sites no escopo.</li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Próximas etapas</td><td><ul><li>Configurar requisitos de arquivo de configuração de avaliação de rede para sites no escopo.</li><li>Execute a validação de conectividade e desempenho de rede para sites no escopo.</li></ul></td></tr>
</table>



### <a name="document-network-connectivity-and-performance-validation-test-results"></a>Documentar a conectividade de rede e os resultados do teste de validação de desempenho

Depois de concluir toda a conectividade de rede e os testes de desempenho dos sites no escopo, crie um relatório que resuma os resultados do teste e apresente-o durante a próxima revisão do Comitê de direção.

#### <a name="site-a-network-connectivity-and-performance-summary-report"></a>Site A: relatório de Resumo de desempenho e conectividade de rede

> [!TIP]
> Veja a seguir um exemplo de exemplo de conectividade de rede e Resumo de desempenho que você pode usar durante a próxima revisão do Comitê de direção durante a determinação da preparação geral da rede para sites em escopo.

**Localização: Seattle [Inside Wired] cliente para o Office 365 resultados**

**Resumo dos resultados**&nbsp; &nbsp; &nbsp; :&#9744;&nbsp; &nbsp; &nbsp; passar &#9744;&nbsp; &nbsp; parcial&nbsp; &#9744;falha 



| Indicador                                                        | Destino                                                                                                             | Dia da semana: o horário comercial do 9:30 está a 11:00                                                                                                                                                                                                                                                                                                 | Dia da semana: horário do Office: 2:30 PM a 4:30 PM | Dia da semana: após horas de 10:30 a 12:30 AM | Fim de semana: após as horas de 9:30 de AM a 11:30 AM | Fim de semana: após horas de 2:30 a 4:30 PM |
|---------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------|-------------------------------------------|------------------------------------------|-----------------------------------------
| Latência (de uma maneira)                                             | \<50 ms                                                                                                           | 40 MS                                                                                                                                                                                                                                                                                                                                     | 38 MS                                    | 41 MS                                     | 35 MS                                    | 36 MS                                   |
| Latência (tempo de ida e volta ou RTT)                             | \<100 ms                                                                                                          | 81 MS                                                                                                                                                                                                                                                                                                                                     | 77 MS                                    | 80 MS                                     | 72 MS                                    | 70 MS                                   |
| Perda de pacote intermitente                                             | \<10% durante qualquer 200-MS Interval                                                                                  | 3%                                                                                                                                                                                                                                                                                                                                        | 2                                       | 2                                        | 0,2%                                     | 0,1%                                    |
| Perda de pacote                                                   | \<1% durante qualquer intervalo de 15 segundos                                                                                   | 0,4%                                                                                                                                                                                                                                                                                                                                      | 0,3%                                     | 0,3%                                      | 0,1%                                     | 0%                                      |
| Tremulação entre entradas do pacote                                   | \<30 ms durante qualquer intervalo de 15 segundos                                                                                | 12 MS                                                                                                                                                                                                                                                                                                                                     | 11 MS                                    | 13 MS                                     | 5 ms                                     | 5 ms                                    |
| Reordenação de pacotes                                                | \<0, 5% de pacotes fora da ordem                                                                                      | 0%                                                                                                                                                                                                                                                                                                                                        | 0%                                       | 0%                                        | 0%                                       | 0%                                      |



<table>
<tr><th colspan="2">Destaques do teste </th></tr>
<tr><td>A ser determinado</td><td>A ser determinado</td></tr>
<tr><th colspan="2">Testando lowlights  </th></tr> 
<tr><td><strong>Problema</strong>: alta latência</td><td><strong>Correção:</strong> Investigue o roteamento de pacotes e implemente a rota ideal.</td></tr>
<tr><td><strong>Problema</strong>: o tempo de viagem de ida e volta não&#39;o dobro da latência</td><td><strong>Correção:</strong> Investigue um possível problema de configuração de firewall ou de roteador. Investigue os caminhos de tráfego.</td></tr>
<tr><td><strong>Problema</strong>: alta perda de pacote </td><td><strong>Correção:</strong> Verifique o planejador de rede em que a largura de banda suficiente foi atribuída. </td></tr>
<tr><td><strong>Problema</strong>: tremulação alta </td><td> <strong>Correção:</strong> Investigue se os valores corretos do ponto de código de serviços diferenciados (DSCP) estão sendo usados. </td></tr>
<tr><td><strong>Problema</strong>: alta perda de pacote </td><td><strong>Correção:</strong> Investigue a perda de pacotes. </td></tr>
<tr><td><strong>Problema</strong>: reordenação de pacotes altos </td><td><strong>Correção:</strong> Investigue a fila e a largura de banda do roteador. </td></tr>
<tr><th colspan="2">Bloqueadores identificados </td></tr>
<tr><td><strong>Bloqueador</strong>: TBD</td><td><strong>Correção</strong>: TBD</td></tr>
</table>




<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/><br/>Pontos de decisão</td><td><ul><li>Avaliar a avaliação de rede e os resultados dos testes de conectividade para garantir que você atenda aos requisitos descritos em <a href="https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance" data-raw-source="[Media quality and network connectivity performance](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)">qualidade de mídia e desempenho de conectividade de rede</a> para os segmentos do cliente e do segmento de borda.</li><li>Você avaliou recursos de rede para dar suporte a mídia em tempo real para todos os sites no escopo?</li><li> Se a sua rede não foi devidamente avaliada ou você sabe que não é compatível com a mídia em tempo real, você desabilitará os recursos de vídeo e compartilhamento de tela para reduzir o impacto na rede e melhorar a experiência do teams para os usuários?</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Próximas etapas</td><td><ul><li>Documentar os resultados do teste de conectividade e desempenho de rede.</li><li>Executar planos de escalonamento e correção para resolver problemas com sites nos quais não há largura de banda suficiente ou os requisitos de desempenho e conectividade de rede não estão sendo atendidos.</li><li>Agende uma reunião de Comitê de direção para revisar os resultados do resumo do teste.</li><li>Apresente os resultados do resumo do teste ao Comitê de direcionamento para identificar qualquer área que exija remediação.</li></ul></td></tr>
</table>


<a name="execute-subscriber-number-port-validation"></a>Executar a validação da porta do número do assinante
-----------------------------------------

Se você precisa transferir números como parte do fornecimento de recursos de chamada de entrada/saída no sistema telefônico com os serviços de planos de chamada compatíveis com o Microsoft Teams, você deve executar uma porta parcial para um número de serviço. Isso vai ajudá-lo a validar as expectativas, os requisitos e a linha do tempo razoáveis à medida que você terminar de preparar a implantação do sistema telefônico com serviços de planos de chamadas em seu ambiente de produção.

Para concluir uma porta parcial de um número de assinante do seu provedor de serviços PSTN atual para o Microsoft Teams, percorra as etapas descritas abaixo.

#### <a name="step-1"></a>Etapa 1

Identifique o número do teste para o qual você gostaria de fazer a portabilidade do Office 365 como um número de usuário (número do assinante) atribuível para ser atendido pelo sistema telefônico com serviço de planos de chamada no Teams.

> [!IMPORTANT]
>Ao planejar o teste de portabilidade de números, verifique as diretrizes mais recentes para solicitações de portabilidade de números em [perguntas comuns](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transferring-phone-numbers-common-questions)de portabilidade.

#### <a name="step-2"></a>Etapa 2

Identifique e documente todas as informações de conta (incluindo o nome usado para a conta específica) para a operadora atual do número de teste que você está portando.
Em geral, você pode encontrar as informações necessárias na fatura ou fatura mais recente do seu provedor de serviços atual.

> [!TIP]
>   Você pode portar ou transferir números de telefone dentro de todos os países/regiões com suporte no momento; no entanto, a maneira pela qual você envia uma solicitação de pedido de portabilidade pode variar de acordo com o país/região do qual os números de telefone são originados. Para obter a lista mais recente de países/regiões com suporte no momento, consulte [disponibilidade de países e regiões para conferências de áudio e planos de chamadas](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).
> 
>   Para obter informações adicionais sobre como transferir números de telefone para o sistema telefônico com planos de chamada, juntamente com possíveis restrições, consulte [transferir números de telefone para o Office 365](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365) e [chamadas de discagem gratuitas dentro do Office 365](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/toll-free-dialing-limitations-and-restrictions.).

#### <a name="step-3"></a>Etapa 3

Baixe e crie uma carta de autorização (LOA) para seu país/região com base no "número de serviço" como o tipo de portabilidade de número.

>[!NOTE]
>   Como os formatos LOA podem ser diferentes por país, região ou tipo de número (ou seja, não geográfico ou número de usuário versus serviço ou número de chamada gratuita), verifique se você está usando o modelo de LOA correto para o seu tipo de cenário específico. Consulte [baixar uma carta de autorização (Loa)](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/download-a-letter-of-authorization-loa) para obter mais informações sobre como escolher o loa ou ir diretamente para a [página de download](https://www.microsoft.com/download/details.aspx?id=49167).

>[!NOTE]
> **Estados Unidos apenas**<br/>
>   Como estamos apenas fazendo a portabilidade de um número de serviço para esse teste, certifique-se de selecionar os campos apropriados no LOA, conforme mostrado abaixo:

![Quantos números de telefone você vai transferir? Resposta: Estou apenas transferindo alguns dos meus números da minha transportadora atual.] (media/onboarding-test-plan-image1.png "Quantos números de telefone você vai transferir? Resposta: Estou apenas transferindo alguns dos meus números da minha transportadora atual.")

![Que tipo de número de telefone você vai transferir? Resposta: Estou transferindo números de telefone de serviço de voz como para atendedores automáticos ou pontes de conferência.] (media/onboarding-test-plan-image2.png "Que tipo de número de telefone você vai transferir? Resposta: Estou transferindo números de telefone de serviço de voz como para atendedores automáticos ou pontes de conferência.")

>[!IMPORTANT]
>   Ao portar números de telefone manualmente usando um LOA, verifique se você selecionou o tipo correto de número de telefone. Você deve enviar pedidos de porta separados para cada tipo de número de telefone que deseja transferir.<br/><br/>
>   Como queremos testar o processo de portabilidade de número usando um número de telefone associado ao mesmo número de telefone de cobrança (BTN), você precisa garantir que o número de telefone de cobrança *não* esteja incluído com o número de telefone específico sendo portado.

#### <a name="step-4"></a>Etapa 4

No portal de administração de locatários, vá para a guia **suporte** e crie e envie uma solicitação de serviço. Anexe o arquivo LOA concluído para agendar o número de telefone associado ao provedor de serviços atual para migração. Para escolher o método de solicitação de serviço mais apropriado para o tamanho do locatário, consulte [Enviar manualmente uma solicitação de serviço personalizada](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/manually-submit-a-custom-service-request).

Depois que a solicitação de suporte for recebida, o suporte da Microsoft acompanhará com base no método de comunicação escolhido e aconselharemos o status e as próximas etapas para concluir o processo de portabilidade de número.

#### <a name="step-5"></a>Etapa 5

Depois que o número é confirmado como tendo sido portado como um novo número do Assinante no Office 365, atribua o número ao sistema telefônico com o serviço de planos de chamadas acessando \> o portal do administrador do locatário do **Centro** \> **de administração do Skype for Business Voz**. Na guia **números de telefone** , atribua o novo número de serviço ao sistema telefônico com o serviço de planos de chamada.

> [!TIP]
>   Embora esta tarefa atribua um novo número de serviço ao sistema telefônico com planos de chamada, no momento da redação, a administração desta tarefa é concluída usando o centro de administração do Skype for Business.

#### <a name="step-6"></a>Etapa 6

Agora que você atribuiu o número do assinante portado, entre em um cliente do teams como usuário e disque um número de 10 dígitos externo por meio da PSTN. Depois de fazer a chamada, confirme se a chamada foi conectada e se a identificação de chamadas exibida corresponde ao número do Assinante que você portou.

#### <a name="step-7"></a>Etapa 7

Em um número PSTN externo, faça uma chamada para o número do Assinante que você portou para o Office 365 e verifique se a chamada é recebida e conectada por meio do cliente do teams.



<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/><br/>Pontos de decisão</td><td><ul><li>Decida quais números de assinantes locais você precisará portar, por país/região.</li><li>Decida qual modelo de LOA você usará.</li><li>Determine se a sua operadora atual (transportadora transportadora) permite a fragmentação do número de telefone (isto é, permite pedidos de porta parcial).</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Próximas etapas</td><td><ul><li>Reúna as informações necessárias e prepare o LOAs.</li><li>Baixe e complete os modelos de LOA de que você precisa.</li><li>Envie uma solicitação de portabilidade de número do Assinante.</li><li>Execute a validação de teste para números portados atribuindo-os ao sistema telefônico com serviço de planos de chamada para acesso de discagem e confirme se eles funcionam, conforme descrito nas etapas 6 e 7 anteriores desta seção.</li></ul></td></tr>
</table>


### <a name="document-service-number-porting-test-results"></a>Resultados do teste de portabilidade de número de serviço de documento

Depois de concluir todos os testes de número do Assinante, crie um relatório que resuma os resultados do teste para apresentar durante a próxima revisão do Comitê de direção.

#### <a name="site-a-number-porting-test-summary-report"></a>Site A: relatório de Resumo de teste de portabilidade de número

> [!TIP]
>   Veja a seguir um exemplo de modelo de relatório de Resumo de teste que você pode usar para analisar durante a próxima reunião do Comitê de direcionamento quando estiver decidindo quando o sistema telefônico integrado com serviços de planos de chamadas na fase piloto.

**Portabilidade do número de serviço**

**Resumo dos resultados**&nbsp; &nbsp; &nbsp; :&#9744;&nbsp; &nbsp; &nbsp; passar &#9744;&nbsp; &nbsp; parcial&nbsp; &#9744;falha 

<table>
<tr><th colspan="2">Destaques do teste </th></tr>
<tr><td>A ser determinado</td><td>A ser determinado</td></tr>
<tr><th colspan="2">Testando lowlights  </th></tr><br/><tr><td><strong>Problema</strong>: TBD</td><td><strong>Correção:</strong> A ser determinado</td></tr>
<tr><th colspan="2">Bloqueadores identificados </td></tr>
<tr><td><strong>Bloqueador</strong>: TBD</td><td><strong>Correção</strong>: TBD</td></tr>
</table>


> [!TIP]
>   Para facilitar mais discussão durante a revisão do Comitê de direcionamento final, você pode usar a [matriz de resultados de teste](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_21) atualizada fornecida pelo myadvisor para documentar e destacar áreas de teste adicionais que exigem correção. [](https://myadvisor.fasttrack.microsoft.com/)


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/><br/>Pontos de decisão</td><td><ul><li>Avalie se os números de assinantes enviados para a migração foram portados com êxito para o sistema telefônico com o serviço de planos de chamada..</li><li>Avalie se você pôde atribuir o número de serviço portado ao sistema telefônico com o serviço de planos de chamada.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Próximas etapas</td><td><ul><li>Documentar os resultados do teste de portabilidade de número.</li><li>Execute planos de escalonamento e correção para resolver problemas que você experimentou com o processo de portabilidade de número, se houver.</li><li>Agende uma reunião de Comitê de direção para revisar os resultados do resumo do teste.</li><li>Apresente os resultados do resumo do teste ao Comitê de direcionamento para identificar qualquer área que exija remediação.</li></ul></td></tr>
</table>


<a name="execute-your-test-plan-for-phone-system-with-calling-plans"></a>Executar seu plano de teste para o sistema telefônico com planos de chamada
----------------------------------------------------------

Agora que você definiu seu plano de teste, a próxima etapa é percorrer os casos de teste, enfocando a avaliação do sistema de telefonia com recursos de administração e experiência do usuário para a administração de planos de chamadas no escopo. Antes de começar a começar, verifique se os pré-requisitos de teste listados abaixo estão corretos.

### <a name="phone-system-with-calling-plans-testing-prerequisites"></a>Sistema telefônico com planos de chamada testando pré-requisitos

-   Os casos de uso empresarial foram definidos para o sistema telefônico com o serviço de planos de chamada.

-   Os principais interessados foram identificados.

-   O licenciamento necessário para o sistema telefônico com serviços de planos de chamada está disponível e foi atribuído ao grupo de usuários no escopo.

-   A lista de sites organizacionais e grupos de usuários no escopo foi identificada.

-   [Créditos de comunicações](what-are-communications-credits.md) (se necessário) foram configurados para sua organização.

-   Sistema telefônico com configurações de planos de chamada foram identificadas e configuradas.

-   As configurações de plano de discagem de locatário que dão suporte ao sistema telefônico com planos de chamada foram identificadas, configuradas e aplicadas para o grupo de usuários no escopo.

-   O sistema telefônico com políticas de planos de chamada foi identificado e configurado para o grupo de usuários no escopo.

-   Os requisitos de conformidade do sistema telefônico com planos de chamada foram identificados e configurados para o grupo de usuários no escopo.

### <a name="document-phone-system-with-calling-plans-test-case-passfail-status"></a>Sistema de telefone de documento com planos de chamada status de aprovação/reprovação de caso de teste

Como os casos de teste são avaliados para os recursos administrativos e do sistema de telefone do usuário do teams em escopo, rastreie os resultados de cada caso de teste para refletir o status de passagem/parcial/falha, juntamente com a ID atribuída do defeito em caso de problemas inesperados.

#### <a name="phone-system-with-calling-plans-test-case-status"></a>Sistema telefônico com planos de chamada status do caso de teste

> [!TIP]
>   Veja a seguir um exemplo de modelo de status de caso de teste que você pode usar para documentar os resultados do teste para revisão durante a próxima reunião do Comitê de direcionamento quando estiver decidindo quando usar o sistema de telefonia integrado com serviços de planos de chamadas na fase piloto.

| Sistema telefônico com planos de chamada          |                              |                                                                                            |                           |                                                                            |
|------------------------------------------|------------------------------|--------------------------------------------------------------------------------------------|---------------------------|----------------------------------------------------------------------------|
| ID do caso de teste                             | Título do caso de teste              | Descrição do caso de teste                                                                      | Resumo dos resultados do caso de teste | ID do defeito atribuído (se aplicável)                                         |
| 1                                        | Colocar chamadas PSTN de saída. | Faça uma chamada de saída discando um número de 10 dígitos doméstico.                              |    &#9744;passar<br/>&#9744;parcial<br/> Falha na &#9744;                   | Quando um usuário insere um número de quatro dígitos, a chamada feita para a PSTN falha. |



<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/><br/>Pontos de decisão</td><td><ul><li>Avaliar o status de aprovação/reprovação de caso de teste de alto nível por site para o sistema telefônico com recursos de planos de chamada no escopo.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Próximas etapas</td><td><ul><li>Documentar os resultados do status do caso de teste para todos os casos de teste concluídos no escopo.</li><li>Agende uma reunião de Comitê de direção para revisar os resultados do resumo do teste.</li><li>Apresentar resultados do status do caso de teste para o Comitê de direcionamento para identificar qualquer área que exija remediação.</li></ul></td></tr>
</table>


### <a name="document-phone-system-with-calling-plans-testing-result-summary"></a>Sistema de telefone de documento com Resumo de resultados de teste de planos de chamada

Depois que todos os casos de teste que dão suporte ao sistema telefônico com recursos de planos de chamada no escopo tiverem sido concluídos pelo site, documente os resultados a serem revisados durante uma reunião do Comitê de direcionamento quando você estiver decidindo quando habilitar o sistema telefônico com serviços de planos de chamada no piloto fases.

#### <a name="site-a-phone-system-with-calling-plans-test-case-summary-report"></a>Site A: sistema telefônico com planos de chamada relatório de Resumo de casos de teste:

> [!TIP]
>   Veja a seguir um exemplo de modelo de relatório de Resumo de teste que você pode examinar durante a próxima reunião do Comitê de direcionamento quando estiver decidindo quando deseja usar o sistema de telefonia integrado com serviços de planos de chamada na fase piloto.


**Sistema telefônico Teams com planos de chamada**

**Resumo dos resultados**&nbsp; &nbsp; &nbsp; :&#9744;&nbsp; &nbsp; &nbsp; passar &#9744;&nbsp; &nbsp; parcial&nbsp; &#9744;falha 

<table>
<tr><th colspan="2">Destaques do teste </th></tr>
<tr><td>A ser determinado</td><td>A ser determinado</td></tr>
<tr><th colspan="2">Testando lowlights  </th></tr><br/><tr><td><strong>Problema</strong>: TBD</td><td><strong>Correção:</strong> A ser determinado</td></tr>
<tr><th colspan="2">Bloqueadores identificados </td></tr>
<tr><td><strong>Bloqueador</strong>: TBD</td><td><strong>Correção</strong>: TBD</td></tr>
</table>


> [!TIP]
>   Para facilitar mais discussão durante a revisão do Comitê de direcionamento final, você pode usar a [matriz de resultados de teste](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_21) atualizada fornecida pelo myadvisor para documentar e destacar áreas adicionais que exigem correção. [](https://myadvisor.fasttrack.microsoft.com/)



<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/><br/>Pontos de decisão</td><td><ul><li>Avaliar resultados de Resumo de teste de alto nível por site para o sistema telefônico com recursos de planos de chamada no escopo.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Próximas etapas</td><td><ul><li>Documentar o relatório de resumo do caso de teste após a conclusão de todos os resultados dos casos de teste.</li><li>Agende uma reunião de Comitê de direção para revisar os resultados do resumo do teste.</li><li>Apresente os resultados do resumo do teste ao Comitê de direcionamento para identificar qualquer área que exija remediação.</li></ul></td></tr>
</table>



<a name="present-and-report-phone-system-with-calling-plans-test-findings"></a>Apresentar e informar o sistema telefônico com resultados de teste de planos de chamada
----------------------------------------------------------------

Depois que todas as atividades de teste tiverem sido concluídas e quaisquer defeitos com o impacto de baixo terem sido resolvidos, agende uma reunião de fechamento final com os participantes do teste designado. Na reunião, endereço:

-   Resumo do status

-   Realçar/lowlights

-   Aulas aprendidas

-   Recomendação geral — vá para a fase piloto ou reavalie os resultados dos testes?

-   Resultados da matriz de teste (elas devem ser totalmente documentadas em um apêndice)

#### <a name="test-plan-deliverables"></a>Resultados do plano de teste:

> [!TIP]
>   Veja a seguir um exemplo de um modelo de entrega de plano de teste que você pode usar para documentar os critérios necessários para obter a aprovação e sair da fase de teste ou suspender o teste até que todos os problemas identificados sejam totalmente resolvidos.

| Resumo do status               | Destaques/lowlights | Aulas aprendidas | Recomendação de fechamento |
|------------------------------|----------------------|-----------------|------------------------|
| <ul><li>Taxa de aprovação de casos de teste de TBD%</li><li>Todos os testes aprovados</li></ul> | A ser determinado                  | A ser determinado             | Ir para o piloto       |

-   Todos os testes aprovados


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/><br/>Pontos de decisão</td><td><ul><li>Decida o resumo do status de teste.</li><li>Identificar realces de teste e lowlights.</li><li>Identifique aulas aprendidas.</li><li>Decidir quais ações de correção permanecerão, se houver.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Próximas etapas</td><td><ul><li>Resultados do resumo do teste de documento a serem incluídos:<ul><li>Resumo do status</li><li>Destaques/lowlights</li><li>Aulas aprendidas</li></ul></li><li>Agende uma reunião de Comitê de direcionamento final para analisar os resultados do teste.</li><li>Apresente os resultados do resumo do teste durante uma revisão do Comitê de direcionamento para obter a aprovação final para sair da fase de teste.</li></ul></td></tr>
</table>
