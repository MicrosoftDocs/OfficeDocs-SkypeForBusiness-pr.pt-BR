---
title: Enterprise testar o plano para o sistema telefônico com planos de chamada no Microsoft Teams
author: rmw2890
ms.author: MyAdvisor
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Valide que as expectativas da sua organização sejam atendidas por meio de testes de sistema telefônico em recursos de equipes, a funcionalidade e usabilidade.
localization_priority: Priority
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: fceaa215835b5ef231a29f896656835da940dbde
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2018
ms.locfileid: "23779802"
---
<a name="define-and-document-your-phone-system-with-calling-plans-in-teams-test-plan-for-enterprises"></a>Definir e documentar o seu sistema telefônico com planos de chamada no plano de teste de equipes para empresas 
============================================================================================

Depois de definidas e documentadas seu sistema telefônico com planos de chamar o sucesso de negócios equipes e planos de implementação técnica como parte da fase Envision, a próxima etapa é Validando expectativas de sua organização e requisitos são atendidos através recurso, a funcionalidade e usabilidade. Você deve realizar esta etapa de validação antes de implantar uma implantação piloto ou final em seu ambiente de produção.

Você pode aproveitar o plano de sucesso de negócios que você definiu durante a fase de Envision para servir como base para determinar as atividades, as expectativas, casos de teste de funcionalidade do recurso e escopo geral a ser avaliada durante a fase de teste.

<a name="identify-testing-support-stakeholders"></a>Identificar participantes de suporte de teste
-------------------------------------

Como se preparar para avaliar o sistema telefônico com recursos de chamada planos, crie uma matriz das partes interessadas de suporte teste para identificar as funções necessárias para dar suporte a fase de teste.

> [!TIP]
> Conforme você popular as equipes de teste a matriz de suporte do interessado, talvez você veja que algumas funções são os mesmos identificados durante a fase de Envision, mas com descrições da função inclinadas em direção de teste. Você pode precisar identificar funções adicionais, dependendo dos requisitos exclusivos do seus cenários de testes.

#### <a name="teams-testing-support-stakeholder-matrix"></a>Equipes de teste a matriz de suporte do interessado

> [!TIP]

> A seguir está um exemplo de um modelo das partes interessadas suporte teste que você pode usar nas quais os participantes que você necessita para dar suporte a fase de teste do documento.

| Função                          | Descrição da função                                                                                                                                                                          | Recurso atribuído, informações de contato e local |
|-------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------|
| Testando patrocinadores executivos  | <ul><li>Certifique-se de que os recursos de equipes atender às necessidades de negócios; os responsáveis executivos são fluentes nos resultados de negócios e cenários de caso de uso priorizada.</li><li>Servir como autoridade ultimate e pressupõem accountability, para o recurso de equipes objetivos de teste.</li><li>Ajuda a resolver problemas escalonados pelo líder de testes.</li><li>Patrocinar comunicação dentro da empresa sobre metas de teste.</li><li>Se responsáveis pela tomada de decisões estratégicas principais.</li><li>Se responsável por garantir a disponibilidade dos recursos necessários e o orçamento para suporte os esforços de teste.</li><li>Unidade conscientização e apoio da direção da campanha de teste com outros participantes principais.</li><li>Servir como patrocinador teste durante a fase de avaliação de teste.</li></ul>                                                 | TBD                                                  |
| Membros do Comitê de direcionamento    | <ul><li>Manter interesse em e oferecem orientação para a direção geral do sistema telefônico com chamar planos de implantação do serviço.<li>Auxiliam na divulgar visão estratégica por meio de dirigir apoio da direção em toda a organização.</li></ul>                                                                        | TBD                                                  |
| Líder de projeto                  |<ul><li> Gerenciar e levam a equipe de projeto.</li><li>Coordene parceiros e equipes de trabalho envolvidas no projeto.</li><li>Ser responsáveis pela criação e planos de gerenciamento de projeto atender aos resultados principais trimestrais.</li><li>Resolva problemas interfuncionais.</li><li>Fornecer atualizações regulares para responsáveis pelo projeto.</li><li>Incorpore lições de experiência do usuário principais identificadas nos resultados de teste para o plano de adoção geral do usuário.</li><li>Liderança business mensais e revisões operacionais, contribuir para trimestral análises dos negócios.</li></ul>                                                                                                                                                         | TBD                                                  |
| Líder/arquiteto de colaboração  | <ul><li>Se responsável por executar sobre a estratégia de colaboração definida por executivos da empresa.</li><li>Analisar e escolha produtos de colaboração para a empresa que atendam aos objetivos de negócios.</li><li>Se responsável pelo design das operações para os produtos de colaboração.</li><li>Defina os modelos de suporte e operação.</li><li>Contribui para análises de negócios mensais e trimestrais.</li></ul>                                                                                                 | TBD                                                  |
| Gerente de projetos               | <ul><li>Desenvolver e manter o plano de projeto.</li><li>Gerencie entregas do projeto alinhado com o plano de projeto e o orçamento.</li><li>Gravar e gerenciar problemas do projeto, incluindo escalações.</li><li>Realize chamadas standup semanais.</li><li>Faça a conexão com e fornecer, aos executivos responsáveis pelo projeto atualizações.</li><li>Trabalhe com equipes de comunicação e gerenciamento de alteração interno para atualizar as alteração abordagem e comunicação planos de gerenciamento conforme necessário.</li></ul>                                                                                                                                                   | TBD                                                  |
| Líder de rede                  | <ul><li>Fornecer informações sobre o design da rede durante a fase de descoberta.</li><li>Participe durante Envision workshops de fase de planejamento.</li><li>Coordene o trabalho da equipe de rede durante a execução do projeto.</li></ul>                                                                                                                               | TBD                                                  |
| Líder de segurança                 | <ul><li>Forneça entrada no design de segurança e processos durante a fase de descoberta.</li><li>Participe durante Envision workshops de fase de planejamento.</li><li>Coordene o trabalho da equipe de segurança durante a execução do projeto.</li></ul>                                                                                                                | TBD                                                  |
| Líder de telefonia                | <ul><li>Durante a fase de descoberta podem inserir comentários sobre o design de telefonia.</li><li>Participe durante Envision workshops de fase de planejamento.</li><li>Coordene o trabalho da equipe de telefonia durante a execução do projeto.</li></ul>                                                                                                                           | TBD                                                  |
| Líder de desktop                  | <ul><li>Fornecer entrada em clientes e o processo de atualização durante a fase de descoberta.</li><li>Participe durante Envision workshops de fase de planejamento.</li><li>Coordene o trabalho da equipe de área de trabalho durante a execução do projeto.</li></ul>                                                                                                              | TBD                                                  |
| Representantes das unidades de negócios | <ul><li>Contribuir para guias de adoção baseada no usuário e materiais.</li><li>Contribuir para e revisar, casos de uso de negócios.</li></ul>                                                                                                                                   | TBD                                                  |
| Administradores de TI                     | <ul><li>Assistência com o planejamento de teste e execução (essa função é para profissionais de TI).                                                                                                                       | TBD                                                  |
| Proprietário do serviço                 | <ul><li>Se responsável pela operação do sistema telefônico com chamar planos de serviço, sempre para cima.</li><li>Servir como o proprietário de um sistema telefônico com planos de chamar o serviço.</li></ul>                                                                                                               | TBD                                                  |
| Gerente/líder de teste             | <ul><li>Defina o plano de teste, incluindo atividades, dependências, ambiente, objetivos, estratégia, envolvimento (ambiental e humano) e a linha do tempo necessário para dar suporte a fase de teste.</li><li>Coordene a entrega e preparação para dependências de plano de teste.</li><li>Alinhe com a prioridade correta para resolução de defeito.</li><li>Servir como o caminho de escalação para quaisquer problemas de testes que surgem.</li><li>Se comunicar e relatar o status do plano de teste com equipes internas e as partes interessadas designadas.</li><li>Documentar e apresentar os resultados do teste final.</li></ul> | TBD                                                  |
| Sistema telefônico com a chamada Testador de planos     | <ul><li>Revise o plano de teste para entender o teste requisitos, objetivos, cronograma, resolução de problemas e casos de teste a ser executado.</li><li>Revise e desenvolver casos de teste que suportam o sistema telefônico com requisitos de aceitação e funcionalidade chamar planos.</li><li>Execute casos de teste e resultados de teste do documento.</li><li>Quando eles surgem e escalá-las para o líder de teste para a priorização e resolução do documento defeitos.</li><li>Teste perdas para fechar o check-out defeitos após ter sido confirmada defeito resolução.</li></ul>                                                                | TBD                                                  |
| Testador de rede                | <ul><li>Revise o plano de teste para entender o teste requisitos, objetivos, cronograma, resolução de problemas e casos de teste a ser executado.</li><li>Examine os requisitos de desempenho e a aceitação de preparação de rede de suporte de casos de teste.</li><li>Execute testes relacionados a preparação da rede, incluindo a conectividade de rede e validação de desempenho, validação de QoS e validação da configuração de divisão de túnel.</li><li>Conclua a validação de largura de banda para sites no escopo usando o Planejador de rede por meio de MyAdvisor.</li><li>Documente os resultados dos testes de preparação da rede.</li><li>Quando eles surgem e escalá-las para o líder de teste para a priorização e resolução do documento defeitos.</li><li>Teste perdas para fechar o check-out defeitos após ter sido confirmada defeito resolução.</li></ul>                                                                | TBD                                                  |
| Testador de segurança               | <ul><li>Revise o plano de teste para entender o teste requisitos, objetivos, cronograma, resolução de problemas e casos de teste a ser executado.</li><li>Revise e desenvolver casos de teste suporte aos requisitos de aceitação de segurança.</li><li>Execute testes relacionados ao aceitação de segurança para os casos de teste.</li><li>Resultados dos testes aceitação de segurança do documento.</li><li>Quando eles surgem e escalá-las para o líder de teste para a priorização e resolução do documento defeitos.</li><li>Teste perdas para fechar o check-out defeitos após ter sido confirmada defeito resolução.</li></ul>                                                                | TBD                                                  |
| Testador de telefonia              | <ul><li>Revise o plano de teste para entender o teste requisitos, objetivos, cronograma, resolução de problemas e casos de teste a ser executado.</li><li>Revise os casos de teste números requisitos portabilidade de aceitação e a funcionalidade do serviço de suporte.</li><li>Execute testes relacionados ao serviço portar número, incluindo a porta de número de serviço para o Office 365.</li><li>Execute casos de teste e resultados de caso de teste do documento.</li><li>Quando eles surgem e escalá-las para o líder de teste para a priorização e resolução do documento defeitos.</li><li>Teste perdas para fechar o check-out defeitos após ter sido confirmada defeito resolução.</li></ul>                                                                | TBD                                                  |
| O sistema telefônico com apenas planos de teste de Admin | <ul><li>Revise o plano de teste para entender o teste requisitos, objetivos, cronograma, resolução de problemas e casos de teste a ser executado.</li><li>Revise e desenvolver casos de teste que suportam o sistema telefônico com planos de chamar aceitação e funcionalidade requisitos de administração.</li> <li>Execute casos de teste e resultados de caso de teste do documento.</li><li>Quando eles surgem e escalá-las para o líder de teste para a priorização e resolução do documento defeitos.</li><li>Teste perdas para fechar o check-out defeitos após ter sido confirmada defeito resolução.</li></ul>                                                                | TBD                                                  |


<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Pontos de decisão</td><td><ul><li>Decida quais funções de suporte e das partes interessadas testing precisar para testar o sistema telefônico com recursos de planos de chamada em seu ambiente.</li><li>Decida quais recursos você atribuirá as funções de suporte e das partes interessadas teste que você identificou.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Próximos passos</td><td><ul><li>As funções de suporte e das partes interessadas testes necessárias em sua matriz das partes interessadas de suporte de testes do documento.</li><li>Informações de contato do documento e detalhes do local para cada recurso forçadas na matriz de teste de suporte das partes interessadas.
</table>


<a name="define-phone-system-with-calling-plans-feature-requirements"></a>Definir o sistema telefônico com planos de chamar os requisitos de recurso 
------------------------------------------------------------

Como parte da definição de sistema telefônico com planos de chamar os requisitos de recurso para usuários no escopo, uma das primeiras etapas que devem ser concluída durante a fase de Envision foi a [Análise de pessoa](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans#assess-environment-and-evaluate-adoption-readiness), onde você definiu seu sistema telefônico com planos de chamada pessoa e cenários.
Com essa linha de base identificada, a próxima etapa é avaliar o mapa de pública mais recente equipes para determinar:

-   Qual sistema de telefone com recursos de planos de chamada que você vai implantar para usuários no escopo.

-   Usuário esperado sistema telefônico com planos de chamar requisitos de funcionalidade, dado o Skype atual para o cenário de implantação de negócios, Exchange e SharePoint.

-   Se você pode confirmar que o sistema telefônico com recursos de planos de chamar descrito no mapa público mais recente para atender a requisitos de escopo na linha do tempo da sua implantação, funcionalidade e usuário

> [!TIP]
> O mapa de equipes mais recente para identificar o sistema telefônico com planos de chamar os recursos no escopo para sua implantação pode ser encontrada em <https://aka.ms/skype2teamsroadmap>.

Agora que o sistema telefônico com recursos e planos de chamar pessoa tiverem sido definidos, o próximo critério para avaliação será a experiência de interoperabilidade com equipes. Para obter informações adicionais sobre a experiência de interoperabilidade, juntamente com as opções de configuração disponíveis, consulte [as equipes da Microsoft e Skype para a interoperabilidade de negócios](https://docs.microsoft.com/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability).

#### <a name="phone-system-with-calling-plans-feature-definition"></a>Sistema telefônico com planos de chamar a definição de recurso

> [!TIP]
> A seguir está um exemplo de um sistema telefônico com planos de chamar modelo de definição que você pode usar para documentar o sistema de telefone com recursos de grupo e usuário de administração planos de chamar a ser avaliada.


| Nível empresarial   | Reuniões colaborativas    | Plataforma e dispositivos   | Para profissionais de TI  | Grupo de negócios adicionais, específicas do site  | Requisitos atendidos pelo mapa de equipes mais recente |
|-------------------------------------------|----------------------------|------------------|------------------------|-------------------|-------------------|
| <ul><li>Sistema telefônico recursos de chamada:<ul><li>Transferência deficientes Visual</li><li>Bloqueio de chamadas</li><li>Encaminhamento de chamadas</li><li>ID do chamador mascaramento</li><li>Suporte do E911</li><li>Extensão de discagem</li><li>Chamada em espera</li><li>Administração de várias chamadas</li><li>Toque simultâneo</li><li>Caixa postal do Azure</li></ul></li><li>Planejamento de chamadas de suporte</li></ul> |<ul><li>Skype para negócios-para-às equipes de chamada</li></ul> |<ul><li> Suporte de recurso do Windows, reuniões com clientes Mac equipes</li><li>Recurso de reuniões de cliente do navegador equipes o suporte para:<ul><li>Chrome</li><li>Microsoft Edge</li></ul></li><li>iOS e suporte ao recurso de reuniões de cliente equipes Android</li><li>Suporte de TTY</li></ul> | <ul><li>Portal de diagnósticos de qualidade de chamada</li><li>Plano de discagem de locatário</li><li>Políticas de ID do chamador locatário</li><li>Habilitar a análise de qualidade de chamada (CQD)</li></ul> | <ul><li>Validar as equipes de recursos com base na imagem de laptop corporativo da reunião</li><li>Suporte de idioma específico</li><li>Configurações do GPO aplicadas para um cenário de determinado usuário ou de um site específico</li></ul> | Sim  |




#### <a name="phone-system-with-calling-plans-user-functionality-definition"></a>Sistema telefônico com planos de chamar definição da funcionalidade de usuário

> [!TIP]
> Veja a seguir um exemplo de um modelo de funcionalidade de usuário que você pode usar para documentar a experiência do usuário necessária baseia-se no sistema de telefone com recursos de planos de chamada a ser avaliada.


| Experiência do Exchange                          | Experiência do SharePoint                            | Experiência de diretiva de interoperabilidade de equipes |
|----------------------------------------------|--------------------------------------------------|------------------------------------------|
| <ul><li>Criar equipes (habilitado para criação de grupo do Office)</li><li>Entrar em equipes</li><li>Criar canais</li><li>Criar e visualizar reuniões</li><li>Modificar fotos de perfil de usuário</li><li>Adicionar e configurar conectores</li><li>Adicionar e configurar guias</li><li>Adicionar e configurar bots</li></ul> | <ul><li>Armazenar e compartilhar arquivos em conversas de equipes</li><li>Armazenamento e compartilhamento e os arquivos dentro de bate-papos privadas (com base em OneDrive)</li></ul> | <ul><li>ChatDefaultClient: padrão</li><li>CallingDefaultClient: padrão</li></ul>      |


<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Pontos de decisão</td><td><ul><li> Decida qual sistema de telefone com recursos de categoria de planos de chamar você vai implantar em seu ambiente.</li><li>Identificar o usuário do seu sistema telefônico com requisitos de funcionalidade de planos de chamar dado seu Skype atual para o cenário de implantação de negócios, Exchange e SharePoint.</li><li>Decida qual experiência de interoperabilidade de equipes que você vai implantar.</li><li>Revise o mapa de pública mais recente equipes e decidir se os recursos de carga de trabalho atuais atendem o cronograma de implantação.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Próximos passos</td><td><ul><li>O sistema de telefone com recursos de chamada planos de categoria necessários para dar suporte ao seu sistema telefônico com chamar planos de implantação de documento.</li><li>Usuário do documento sistema telefônico com planos de chamar a funcionalidade e os requisitos de interoperabilidade fornecidos sua Skype atual para o cenário de implantação de negócios, Exchange e SharePoint.</li><li>Se o mapa de pública equipes mais recente que representam o sistema telefônico com recursos de planos de chamar atende às necessidades de negócios e requisitos de temporização da sua implantação do documento.</li></ul></td></tr>
</table>

<a name="define-and-document-your-phone-system-with-calling-plans-test-plan"></a>Definir e documentar o seu sistema telefônico com planos de chamar o plano de teste
------------------------------------------------------------------

Depois que você definiu o sistema telefônico com planos de chamar os recursos no escopo, a próxima etapa é criar o plano de teste. Em um alto nível, o plano de teste abrange a estratégia de teste geral e a metodologia que você usará para dar suporte a validação de recurso no processo de teste.

Em um alto nível, o plano de teste deve incluir:

-   **Testes escopo:** Resume as áreas de foco (metas, cenários e objetivos) a ser avaliada como parte da fase de teste

-   **Casos de teste:** O conjunto de casos de teste a ser validado para o sistema telefônico com planos de chamar os recursos no escopo

-   **Recursos de teste:** Uma matriz de recursos necessários para dar suporte a iniciativa de teste de um ponto de vista ambiental, técnicas e pessoal

-   **Agenda de testes (cronograma):** Representa quando o teste terá início, quanto tempo é provável ao último e quando você espera que a fase de teste ao fim

-   **Relatórios e correção de defeitos:** Diretrizes para como problemas com o teste devem ser relatados, controladas e priorizada

-   **Triagem e escalonamento de defeitos:** Tópicos como e quando um escalonamento defeito deve ser iniciado

-   **Testando os critérios de saída e de suspensão:** Critérios de tópicos de orientação para qualquer um dos atingir aprovação para sair a fase de teste ou testes pausando até priorizados defeitos forem resolvidos

-   **Teste material:** Resumo das quais os resultados serão desenvolvidos e entregue para oferecer suporte a aceitação de aprovação e sair do processo de testes

> [!TIP]
>   Uma metodologia de teste talvez já existam em sua organização, mas as diretrizes abaixo refletem as práticas recomendadas que podem ser incluídas ou aproveitadas separadamente para recursos de equipes de teste em seu ambiente.

Nas seções a seguir, você encontrará diretrizes adicionais de indicado que auxiliarão na decisões específicas e os modelos e tópicos a serem consideradas conforme você concluir seu plano de teste.

### <a name="define-and-document-testing-scope"></a>Definir e documentar o escopo de teste

Enquanto você trabalha para desenvolver seu plano de teste, você deve definir o escopo do teste com antecedência, realce a carga de trabalho e a lista dos recursos que você está avaliando.

O escopo para avaliar corretamente o sistema telefônico com planos de chamar recursos normalmente inclui:

-   Sistema telefônico com planos de chamar prontidão do local

-   Sistema telefônico com planos de chamar a experiência do usuário

-   Sistema telefônico com administração de planos de chamada

#### <a name="phone-system-with-calling-plans-testing-scope"></a>Sistema telefônico com chamar planos de teste de escopo

> [!TIP]
>   A seguir está um exemplo de modelo de escopo de teste que você pode usar para documentar o sistema de telefone com recursos de grupo e usuário de administração planos de chamar a ser avaliada.

| Sistema telefônico com planos de chamar prontidão do local                                                                                                                                                                                    | Sistema telefônico com planos de chamar a experiência do usuário                                                                                                                                                                                         | Sistema telefônico com experiência de administração de planos de chamada                                                                           |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| <ul><li>Largura de banda de planejador planejamento (via MyAdvisor) de rede<li></li>Validação de conectividade e desempenho de rede (via Skype para ferramenta de avaliação de rede de negócios)<li></li>Qualidade da validação de serviço (QoS)<li></li>Validação de divisão de túnel de acesso remoto</li></ul>|<ul><li>Recursos do PBX<li></li>PSTN chamar (nacionais e internacionais)<li></li> Fazer e receber chamadas PSTN<li></li>Caixa postal do Azure<li></li>E911<li></li>Plano de discagem de locatário<li></li>Mascaramento de ID do chamador locatário <li></li>Recursos de controle de chamada avançados (por exemplo, chamada encaminhamento, toque simultâneo)</li></ul> |<ul><li>Atribuição de licenciamento</li><li>Número de assinante portando para o Office 365</li><li>Sistema telefônico com o relatório de planos de chamada</li><li>Qualidade da chamada reporting (CQD)</li></ul> |

<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Pontos de decisão</td><td><ul><li>Decida o sistema telefônico com chamar planos de teste escopo identificando recursos sejam avaliados pelo área de foco.</li><li>Decida adicionais metas e objetivos para avaliação.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Próximos passos</td><td><ul><li>O sistema telefônico com planos de chamar os recursos sejam avaliados pelo área de foco do documento.</li><li>Documentos adicionais metas e objetivos para avaliação.</li></ul></td></tr>
</table>

### <a name="define-and-document-phone-system-with-calling-plans-test-cases"></a>Definir e documentar o sistema telefônico com planos de chamar casos de teste

Depois que você definiu o sistema de telefone com recursos de chamada planos, implantação do cliente e cenários lado a lado com Skype para negócios (se aplicável), a próxima etapa é formular os casos de teste necessários para avaliar o sistema telefônico com chamar planos de recursos no escopo. Em um alto nível, casos de teste normalmente são agrupados por área foco e incluem:

-   **Título do caso de teste:** Área de foco do recurso o teste está avaliando (por exemplo, o sistema telefônico com planos de chamar)

-   **Descrição do caso de teste:** Recursos de resumo descrevendo os objetivos do teste está sendo avaliada

-   **Instruções de caso de teste:** Etapas a serem seguidas para executar corretamente o caso de teste está sendo executado

-   **Ambiente necessário (pré-requisitos):** Instruções de configuração necessárias para o teste seja executado apropriadamente

-   **Recurso necessário:** Recursos de pessoal necessário para avaliação adequada e a execução do teste

-   **Resultados esperados:** O resultado esperado depois que o teste for concluído com êxito

> [!NOTE]
>   Como a abordagem e o nível de detalhes necessário para a criação de caso de teste podem variar dentro da sua organização, é uma boa ideia siga uma abordagem que permite a um nível de detalhe adequado ainda equilibra a abrangência com a viabilidade, para dar suporte ao teste geral capacidade de gerenciamento.

> [!TIP]
>   Para auxiliar na criação de caso de teste como um ponto de partida, consulte a lista de diretrizes de usuário de sistema de telefone disponível em [equipes reuniões e chamadas](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).

#### <a name="phone-system-with-calling-plans-test-case"></a>Sistema telefônico com planos de chamar o caso de teste

> [!TIP]
>   A seguir está um exemplo de modelo de caso de teste que você pode usar para documentar o sistema de telefone com recursos de grupo e usuário de administração planos de chamar a ser avaliada.

Sistema telefônico com a chamada de validação de planos

| ID do caso de teste | Título do caso de teste               | Descrição do caso de teste                                                  | Ambiente necessário para a execução do caso de teste                                               | Etapas necessárias para a execução do caso de teste                                                                                                                                                          | Testando o recurso necessário              |
|--------------|-------------------------------|------------------------------------------------------------------------|--------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------|
| 1            | Colocar uma chamada PSTN de saída | Verifique se que você pode colocar uma chamada de voz externo para um número de 10 dígitos. |<ul><li>Cliente de equipes instalado.</li><li>Usuário habilitado com as seguintes licenças do Office 365 atribuídas:<ul><li>E5 de Enterprise do Office com o sistema telefônico, as equipes da Microsoft e planos de chamada nacionais e internacionais</li><li>E3 de Enterprise do Office com o sistema telefônico, as equipes da Microsoft e planos de chamada nacionais e internacionais</li></ul></li></ul> | <ol><li>Entrar no cliente de equipes.</li><li>Selecione o teclado de discagem e insira um número de 10 dígitos a serem discados.</li><li>Verifique se a discagem número foram normalizada corretamente e a chamada PSTN externa for estabelecida.</li></ol>    | Sistema telefônico com a chamada Testador de planos |


> [!TIP]
>   Para obter orientação adicional no facilitando o caso de teste individual e a criação de um plano geral para avaliar o sistema telefônico com planos de chamar os recursos em sua organização, examine o [Plano de teste do sistema de telefone](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_21) fornecidos pelo [MyAdvisor](https://myadvisor.fasttrack.microsoft.com/).


<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Pontos de decisão</td><td><ul><li>Decidir qual sistema telefônico com administração de chamar planos e recursos de usuário serão avaliados.</li><li>Decida qual ambiente de teste é necessário para suportar a execução do caso de teste.</li><li>Decida as etapas necessárias para a avaliação do caso de teste.</li><li>Decida os recursos exigidos para a execução do teste adequada.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Próximos passos</td><td><ul><li>Documente os casos de teste a ser avaliada, baseado no modelo de caso de teste fornecido.</li><li>Inclua o modelo concluído como parte do seu plano de teste geral.</li></ul></td></tr>
</table>


### <a name="define-and-document-testing-resources"></a>Definir e documentar os recursos de teste

Para oferecer suporte a fase de teste, é importante que você desenvolva um plano de recursos detalhando os recursos de tecnologia, suporte e as pessoas que você vai precisar. Um componente importante do plano de teste geral, o ajuda a planejar de recurso que determinar quaisquer dependências que podem existir e fornece um senso de alto nível do recurso de suportam que você talvez seja necessário.

Em um alto nível, esses recursos normalmente consistem em:

-   **Pessoas**: participantes

-   **Tecnologia**: locatário, licenciamento, dispositivos

-   **Suporte**: treinamento (cartões, vídeos), o suporte de administração com o caminho de escalonamento definido

#### <a name="testing-resource-requirements"></a>Requisitos de recursos de teste

> [!TIP]
>   Abaixo é um exemplo de teste modelo requisito de recurso que você pode usar para documentar os diferentes tipos de recursos necessários para dar suporte a sua fase de teste.


| Tipo de recurso | Recursos necessários                                           | Descrição do recurso |
|---------------|--------------------------------------------------------------|----------------------|
| Pessoas        | Os testadores Lead de teste de participantes                               | TBD                  |
| Tecnologia    | Acesso ao Office 365 com os seguintes serviços habilitados:<ul><li>Licenciamento do Office 365 E5 atribuído</li><li>Plano de chamada nacionais e internacionais atribuído</li></ul>    | TBD                  |
| Suporte       | Testar o responsável pelo administrador teste suporte técnico de suporte do teste | TBD                  |

<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Pontos de decisão</td><td><ul><li>Decida os tipos de recursos (pessoas, tecnologia e suporte) que você precisará para dar suporte a fase de teste.</li><li>Decida os recursos específicos necessários para os tipos de recursos que você identificou.</li><li>Decida se você deve fornecer mais detalhes para descrever os tipos de recursos que você precisa.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Próximos passos</td><td><ul><li>Documente os tipos de recursos (pessoas, tecnologia e suporte) que você precisará para dar suporte a fase de teste.</li><li>Documente os recursos específicos necessários para os tipos de recursos que você identificou.</li><li>Se você decidir que é necessário, documente qualquer detalhe adicional sobre os tipos de recursos que você precisa oferecer suporte a fase de teste.</li></ul></td></tr>
</table>


### <a name="define-and-document-a-testing-timeline"></a>Definir e documentar um cronograma de teste

Como parte da definição de plano de teste, crie um cronograma que descreve o agendamento para quando você pretende conclua as atividades de testes e atingir as metas de alto nível.

Em um alto nível, isso normalmente consiste em:

-   **Tarefa:** Atividade de alto nível para ser concluída

-   **Milestone:** Meta de alto nível ou andamento concluído

-   **Recurso necessário:** Teste os recursos necessários para dar suporte a entrega da etapa do projeto ou tarefa identificado

-   **Data de início:** A data em que a atividade, a etapa do projeto ou a tarefa foi iniciada em

-   **Data de conclusão:** A data em que você espera que a atividade, etapa do projeto ou tarefa deve ser concluída por

-   **Proprietário:** Recurso atribuído quem é responsável por garantir que a atividade, a etapa do projeto ou a tarefa foi concluída no tempo, de acordo com a data de conclusão

-   **Estimativa:** Número de horas que os recursos atribuídos prevê que ela levará para garantir que a atividade, a etapa do projeto ou a tarefa foi concluída no tempo

#### <a name="testing-scheduling-and-timeline-requirements"></a>Requisitos de agendamento e o cronograma de teste

> [!TIP]
>   Abaixo é um exemplo de um modelo de requisito testing cronograma que você pode usar para documentar as datas previstas para quando as atividades de testes específicas serão concluídas ou marcos viabilizadas pela.

| Tarefa                                                 | Etapa do projeto       | Data de início                                                             | Data de conclusão | Proprietário | Recursos atribuídos | Estimativa |
|------------------------------------------------------|-----------------|------------------------------------------------------------------------|-----------------|-------|--------------------|------------|
| Relatório de teste                                          | TBD             | TBD                                                                    | TBD             | TBD   | TBD                | Horas TBD  |
| Execução do caso de teste: Sistema telefônico com a chamada de planos | TBD             | TBD                                                                    | TBD             | TBD   | TBD                | Horas TBD  |
| Execução do caso de teste: Preparação da rede               | TBD             | TBD                                                                    | TBD             | TBD   | TBD                | Horas TBD  |


<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Pontos de decisão</td><td><ul><li>Decida atividade de cronograma, etapa do projeto e tarefas que você precisa controlar.</li><li>Decida quais recursos você precisará atribuir.</li><li>Decida a data em que você espera que seja feito.</li><li>Identifica o proprietário de entrega.</li><li>Decida quanto tempo levará para concluir a atividade, etapa do projeto ou tarefa.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Próximos passos</td><td><ul><li>Documente o cronograma do teste usando o modelo fornecido e incluem:<ul><li>Linha do tempo atividade, etapa do projeto e tarefas que precisam ser rastreados.</li><li>Recursos que precisam ser atribuídas.</li><li>Data de conclusão previsto.</li><li>Proprietário de entrega.</li><li>Tempo necessário para concluir a atividade, etapa do projeto ou tarefa.</li></ul></li><li>Inclua o modelo concluído como parte do seu plano de teste geral.</li></ul></td></tr>
</table>


### <a name="define-and-document-test-defect-report-criteria"></a>Definir e documentar os critérios de relatório do teste defeito

Como os casos de teste dentro de um determinado fase ou stream são executados, problemas podem surgir onde o resultado do caso de teste está sendo executado não é esperado.

Quando esses tipos de resultados ocorrem, eles devem ser registrados em um plano de relatório e correção de defeitos que será escalonado para o líder de teste designado para revisão, relatórios e resolução de defeito.

Normalmente, um plano de relatório e correção de defeitos inclui o seguinte:

-   **Defeito ID:** O número atribuído ao problema

-   **ID do caso de teste afetado**: O número atribuído para o caso de teste que estava sendo avaliado no momento em que o defeito foi identificado

-   **Defeito Descrição:** Resumo do problema

-   **Ambiente/etapas para reproduzir:** Resumo da instalação de ambiente de teste, juntamente com as etapas necessárias para reproduzir o problema

-   **Gravidade defeito**: O impacto do problema, que varia de impedindo que o caso de teste que está sendo aprovada sendo aceitas com um mínimo de risco. Alguns exemplos podem incluir:

-   **Baixa:** O problema tem pouco impacto e não impedirá que o caso de teste atingir aceitação se o problema pode ser resolvido mais tarde.

-   **Médio:** O problema tem um impacto substancial, mas não impede que o caso de teste atingir aceitação se o problema pode ser resolvido antes que a fase de teste seja concluída.

-   **Alta:** -o problema tem crítico impacto sobre o caso de teste. O problema deve ser resolvido antes que o caso de teste seja aceito.

-   **Status:** Tem o problema foi resolvido, é aberto, ou ainda sob investigação

-   **Enviados por:** O testador que relatou o problema

-   **Atribuído proprietário:** O recurso atribuído da equipe do teste quem é responsável por resolver o problema

-   **Detalhes de suporte:** Isso pode incluir — mas não está limitado a — logs do cliente, capturas de tela ou vídeo do problema.

Como os testadores executados os casos de teste descritos no seu plano de teste, devem ser preencha um plano de relatório e correção de defeitos para quaisquer problemas que podem surgir.
Esse procedimento realçará impacto em potencial que poderia impedem ou até mesmo suspender o processo de avaliação de teste.

#### <a name="testing-defect-report-and-remediation-plan"></a>Plano de teste e remediação de relatório de falhas

> [!TIP]
>   Abaixo é um exemplo de modelo de relatório de falhas e planejar remediação que você pode usar para documentar problemas descobertos durante a fase de teste.

| ID de defeito                                | ID do caso de teste afetado | Descrição de defeito                                                                                 | Ambiente /steps reproduzir                                                                                                | Severidade | Status | Enviado por | Proprietário atribuído | Suporte de detalhes (logs, capturas de tela e assim por diante) |
|------------------------------------------|-----------------------|----------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------|----------|--------|--------------|----------------|---------------------------------------------------|
| 1                                        | 1                     | Quando o usuário insere uma extensão de quatro dígitos, a tentativa de fazer uma chamada de saída, a chamada falhará. | No cliente de equipes, selecione o teclado de discagem, digite uma extensão de quatro dígitos e selecione o ícone de telefone para tentar fazer a chamada. | Médio   | Fechado | Louis Lahr   | Lisa cinza      | Log do lado do cliente de equipes<br/> Captura de tela de cliente de equipes     |


<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Pontos de decisão</td><td><ul><li>Decida quais níveis de severidade defeito critérios você atribuirá para suportar o esforço de teste.</li><li>Decida qual defeito testing reporting critérios que você vai documente se surgem os problemas durante o teste.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Próximos passos</td><td><ul><li>Documente o teste defeito reporting critérios necessários no modelo fornecido.</li><li>Inclua o modelo concluído como parte do seu plano de teste geral.</li></ul></td></tr>
</table>


### <a name="define-and-document-exit-and-suspension-criteria"></a>Definir e documentar os critérios de saída e de suspensão

Como parte do processo geral de execução de plano de teste, você precisará definir critérios para indicar o ponto no qual você deve suspender os esforços de teste versus requisitos que devem ser atendidos para obter aprovação e saindo a fase de teste.

#### <a name="test-plan-exit-and-suspension-criteria"></a>Critérios de suspensão e a saída de plano de teste

> [!TIP]
>   Veja a seguir um exemplo de suspensão e a saída do modelo de critérios que podem ser usados no seu plano de teste aos critérios de documento é necessário obter aprovação, saia a fase de teste ou suspender atividades de testes.

| Teste os critérios de saída                            | Critérios de suspensão de teste                      |
|--------------------------------------------------|--------------------------------------------------|
|<ul><li>Todos os casos de teste deve obter uma taxa de passagem de % TBD</li><li>Todos os casos de teste deve ter sido completamente executados</li><li>De todos os casos de teste avaliados, todos os defeitos alta gravidade devem ser fechados.</li></ul> | <ul><li>Todos os casos de teste deve obter uma taxa de falha de % TBD</li><li>Todos os defeitos identificados como alta gravidade devem ser resolvidos antes de continuar a testar.</li></ul> |


<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Pontos de decisão</td><td><ul><li>Decida quais critérios de suspensão que devem ser atendidos se problemas com o teste são identificados.</li><li>Decida sobre os critérios de saída que devem ser atendidos para obter a teste aceitação aprovação e suporte saindo a fase de teste depois que todos os testes atividades tiverem sido concluídas.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Próximos passos</td><td><ul><li>Documente os critérios de suspensão e a saída testes necessários nos modelos de teste e a saída fornecidos.</li></ul></td></tr>
</table>


### <a name="define-and-document-the-defect-escalation-process"></a>Definir e documentar o processo de escalação defeito

Durante o curso de execução de plano de teste, você pode descobrir um problema ou identificar um defeito que exige escalonamento para o recurso de direito para dirigir e determinar a resolução necessária para permitir que os testes para continuar.

Conforme defeitos são identificados com a gravidade apropriada e a prioridade atribuída, você cria uma matriz de escalonamento e triagem revisar o processo de mapeamento de check-out quando um escalonamento é disparado e como, quando e quem o defeito será atribuído para mais revisão e resolução.

Normalmente, um plano de relatório e correção de defeitos inclui o seguinte:

-   **Defeito ID:** O número que você atribuiu o problema

-   **Defeito Descrição:** Resumo do problema

-   **Avaliação de prioridade de defeitos:** O nível de prioridade atribuída a um defeito para resolução com base no impacto nos negócios e defeito gravidade. Alguns exemplos incluem:

-   **Baixa:** O problema tem pouco impacto sobre impedindo a fase de teste de atingir aprovação, se o problema pode ser resolvido mais tarde.

-   **Médio:** O problema tem um impacto substancial sobre impedindo a fase de teste de atingir aprovação, se o problema não pode ser resolvido.

-   **Alta:** O problema tem crítico impacto sobre impedindo a fase de teste de atingir aprovação, se o problema não pode ser resolvido.

-   **Atribuído defeito proprietário:** O recurso atribuído da equipe do teste quem é responsável por resolver o problema

-   **Atribuído defeito ponto de escalonamento:** O recurso atribuído quem é o ponto para escalar a questão na organização (se necessário) para chegar a resolução; com base na severidade defeito

-   **Defeito status:** Tem o problema foi resolvido, é aberto, ou ainda sob investigação

-   **Necessário resolução por data:** A data em que o problema deve ser resolvido pelos

-   **Data de status:** A data em que reflete o status da última vez foi atualizada como resultado de uma revisão de triagem defeito

#### <a name="test-plan-defect-escalation"></a>Escalonamento de defeito do plano de teste

> [!TIP]
>   Abaixo é um exemplo de um modelo de escalonamento defeito que você pode usar em parte do seu plano de teste para documentar o processo de escalação necessário para a priorização e resolvendo defeitos de testes.

| ID de defeito                                | Descrição de defeito                                                                                 | Avaliação de prioridade de defeito                                           | Proprietário de defeito atribuídas | Ponto de escalonamento de defeito atribuídas | Método de escalonamento de defeito                                          | Status de defeito | Resolução necessária por data | Data de status |
|------------------------------------------|----------------------------------------------------------------------------------------------------|----------------------------------------------------------------------|-----------------------|----------------------------------|-------------------------------------------------------------------|---------------|-----------------------------|-------------|
| 1                                        | Quando o usuário insere uma extensão de quatro dígitos, a tentativa de fazer uma chamada de saída, a chamada falhará. | Médio                                                               | Lisa cinza             | Louis Lahr                       | E-mail de alta prioridade triagem revisão semanal para partes interessadas afetadas | Abra o           | ASAP                        | 1/12/2018   |



<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Pontos de decisão</td><td><ul><li>Decida e concorda nas prioridades defeito para dar suporte ao seu plano de teste.</li><li>Decida o ponto de escalonamento para cada área defeito.</li><li>Decida o escalonamento de defeito e o plano de triagem serem seguidas, com base na prioridade.</li><li>Decida o relatório de defeito e triagem do plano de comunicação para escalonamento.</li><li>Decida a cadência da reunião de revisão triagem defeito.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Próximos passos</td><td><ul><li>Documente as prioridades concordou em defeito.</li><li>Documente o ponto de escalonamento para cada área de foco potencial.</li><li>Documente o plano de escalonamento e a triagem de defeito com base nos critérios acordado.</li><li>Documente seu defeito diretrizes de emissão de relatórios.</li><li>Agende a série de reuniões de triagem defeito.</li></ul></td></tr>
</table>


### <a name="define-and-document-testing-deliverables"></a>Definir e documentar os resultados de testes

O componente final e último na criação de um plano de teste é identificar os resultados em termos de resultados finais específicos que representará o plano de teste geral.

Em um alto nível, esses geralmente incluem, mas não estão limitados a:

-   Plano de teste

-   Casos de teste

-   Relatórios de defeito

-   Resumo de resultados do teste

-   Teste de aceitação e aprovação

#### <a name="test-plan-deliverables"></a>Resultados finais de plano de teste

> [!TIP]
>   A seguir está um exemplo de uma matriz de produto de plano de teste que você pode usar para os produtos a serem criados, juntamente com os recursos necessários para revisão, aprovação e aprovação de documentos.

| Plano de teste do produto                    | Formato de produto de plano de teste | Proprietário do produto do plano de teste                                                                                                      | Revisor de produto de plano de teste | Aprovador de produto de plano de teste | Plano do produto aprovação data do teste |
|------------------------------------------|------------------------------|----------------------------------------------------------------------------------------------------------------------------------|--------------------------------|--------------------------------|-------------------------------------|
| Plano de teste                                | Palavra                         | TBD                                                                                                                              | TBD                            | TBD                            | TBD                                 |
| Relatórios de gerenciamento de defeito                | Palavra                         | TBD                                                                                                                              | TBD                            | TBD                            | TBD                                 |
| Teste os relatórios de status                   | Palavra                         | TBD                                                                                                                              | TBD                            | TBD                            | TBD                                 |
| Resumo de resultados do teste                     | Word PPTX                    | TBD                                                                                                                              | TBD                            | TBD                            | TBD                                 |


<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Pontos de decisão</td><td><ul><li>Decida quais produtos devem ser criadas e capturado como saída de cada fase de teste. Para cada produto, decida sobre seu:<ul><li>Formato</li><li>Proprietário</li><li>Revisor</li><li>Aprovador</li></ul></li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Próximos passos</td><td><ul><li>Um plano produto criação e entrega matriz de teste do documento.</li></ul></td></tr>
</table>


<a name="evaluate-network-readiness"></a>Avaliar a preparação de rede
----------------------------

Como um elemento essencial sua implantação de equipes de suporte, a preparação da rede é uma parte essencial de teste para garantir que a rede corretamente está otimizada para comunicações de equipes de suporte. Para garantir que sua rede está pronta para os sites no escopo, incluem as áreas de foco listadas abaixo na sua estratégia de teste geral:

-   Estimativa de largura de banda e planejamento com Planejador de rede (via MyAdvisor)

-   Qualidade de validação da configuração do serviço (QoS)

-   Verificar a conectividade da rede e o desempenho por meio de simulação de tráfego

-   Validação de divisão de túnel

### <a name="execute-network-planner-through-myadvisor-for-sites-and-personas-in-scope"></a>Executar Planejador de rede (por meio de MyAdvisor) para sites e personagens no escopo

Antes de introduzir serviços de comunicação em tempo real, como equipes em seu ambiente, é importante para garantir que a rede foi corretamente otimizada e em tamanho de um ExpressRoute do Windows Azure (se aplicável), internet e perspectiva de largura de banda WAN.

Para ajudar a determinar o nível de otimização de rede necessária para sites no escopo que oferece suporte a sua implantação e a largura de banda, conclua a ferramenta [Planejador de rede](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner/Help?sectionName=DashboardHelp) (por meio de MyAdvisor) para validar a preparação da rede da sua organização precisa. Para obter orientação adicional sobre como determinar os requisitos de rede para equipes por meio do Planejador de rede, consulte MyAdvisor: Planejador de rede.

> [!TIP]
>   Para obter informações adicionais sobre a guia de **recomendações** , com exemplos de como configurar e interpretar os resultados, consulte a [Visão geral de recomendações](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner/Help?sectionName=RecommendationHelp)do Planejador de rede.



<table>
<tr><td>![](media/audio_conferencing_image7.png)<br/>Pontos de decisão</td><td><ul><li>Decida quais sites de rede estão dentro do escopo para a implantação das equipes de serviços.</li><li>Decida as personagens necessárias para modalidades de equipes em escopo.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Próximos passos</td><td><ul><li>Conclua Planejador de rede (por meio de MyAdvisor) para a lista de sites que estão dentro do escopo.</li><li>Validação de rede Planejador de documento resulta no modelo de resultados de plano de teste fornecido.</li><li>Valide o ExpressRoute (se aplicável), a internet e a largura de banda WAN que foram calculada para sites no escopo alinha com os valores de largura de banda que estão atualmente alocados.</li><li>Para sites que não têm a largura de banda adequada, execute planos de escalação e correção para resolver problemas de largura de banda.</li><li>Estabeleça uma rede de monitoramento de solução para sites no escopo para monitorar o uso de largura de banda e QoS para ExpressRoute (se aplicável), internet e os segmentos de WAN.</li><li>Agende uma reunião comitê de orientação para analisar os resultados de Planejador de rede.</li><li>Apresentar os resultados para o Comitê de orientação para identificar quaisquer áreas que exigem remediação do planejamento de largura de banda.</li></ul></td></tr>
</table>


<a name="evaluate-qos-configuration-for-sites-in-scope"></a>Avaliar a configuração de QoS para sites no escopo
---------------------------------------------

Como parte de validação de preparação da rede para dar suporte a comunicação em tempo real de equipes, é igualmente importante garantir que a rede foi corretamente configurada e otimizada de uma perspectiva de QoS.

Para obter orientação adicional sobre como configurar, implantar e validar a preparação da rede de QoS para equipes usando a diretiva de grupo, consulte [Habilitando QoS para equipes](https://docs.microsoft.com/MicrosoftTeams/qos-in-teams).


<table>
<tr><td>![](media/audio_conferencing_image7.png)<br/>Pontos de decisão</td><td><ul><li>Decida sobre a configuração de QoS a serem implementadas.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Próximos passos</td><td><ul><li>Configure a QoS.</li><li>Execute validação de QoS, conforme destacado de etapas listadas via o "validar via GPO" e "validar por meio do analisador de mensagem" seções acima.</li></ul></td></tr>
</table>


### <a name="document-qos-configuration-validation-test-results"></a>Documente os resultados de testes de validação de configuração de QoS

Depois de concluir testes usando a diretiva de grupo para sites no escopo de validação de QoS, crie um relatório que resume os resultados dos testes para apresentar durante a revisão final comitê de orientação.

#### <a name="site-a-qos-configuration-validation-testing-summary-report"></a>Site r: validação da configuração de QoS testando o relatório de resumo

> [!TIP]
>   Abaixo é um exemplo de modelo de relatório de resumo que você possa examinar durante a próxima reunião comitê de direcionamento ao decidir quando para onboard sistema telefônico com planos de chamar serviços na fase piloto de teste.


**Validação da configuração de QoS por meio do GPO e o analisador de mensagem**

**Resumo dos resultados**:&nbsp;&nbsp;&nbsp;& #9744; Passe&nbsp; &nbsp; &nbsp; & #9744; Parcial&nbsp; &nbsp; &nbsp; & #9744; Falhar

<table>
<tr><th colspan="2">Destaques de teste </th></tr>
<tr><td>TBD</td><td>TBD</td></tr>
<tr><th colspan="2">Testando pontos menos importantes  </th></tr>  
<tr><td>**Problema**: TBD</td><td>**Remediação:** TBD</td></tr>
<tr><th colspan="2">Bloqueadores identificados </td></tr>
<tr><td>**Bloqueador**: TBD</td><td>**Correção**: TBD</td></tr>
</table>


> [!TIP]
> Para facilitar a discussão adicional durante a revisão final comitê de orientação, você pode usar atualizado [matriz de resultados de testes](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_21) de [MyAdvisor](https://myadvisor.fasttrack.microsoft.com/) para documentar e destacar áreas adicionais que exigem remediação.



<table>
<tr><td>![](media/audio_conferencing_image7.png)<br/>Pontos de decisão</td><td><ul><li>Avaliar os resultados do teste de QoS para garantir que as equipes de tráfego de mídia em tempo real está sendo adequadamente marcado e priorizados.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Próximos passos</td><td><ul><li>Resultados do teste de QoS de documento no modelo de resultado do plano de teste fornecido.</li><li>Execute planos de escalação e correção para resolver problemas onde QoS pode não estar configurado corretamente ou não funcionar como esperado para suportar o tráfego de mídia de equipes.</li></ul></td></tr><li>Agende uma reunião comitê de orientação para revisar o resumo de resultados de teste.</li><li>Presente teste resumo de resultados para o Comitê de orientação para identificar quaisquer áreas que exigem remediação.</li>
</table>


<a name="execute-split-tunnel-enablement-validation"></a>Executar a validação de habilitação de divisão de túnel
------------------------------------------

É comum para empresas hoje ter uma ou mais soluções para fornecer acesso remoto, como uma rede virtual privada, ou VPN. Essas soluções permitem conectividade com aplicativos e ativos de linha de negócios internos de forma segura e confiável.

Embora as soluções de acesso remoto podem funcionar muito bem para fornecer acesso para alguns aplicativos, quando se trata de tráfego de mídia em tempo real de equipes de encapsulamento, essas soluções frequentemente resultam em uma experiência de usuário menos ideal para todos os participantes em um áudio de equipes cenário de chamada ou de conferência.

Para garantir que o tráfego de mídia de equipes faz *desviar soluções de acesso remoto em seu ambiente* , será necessária uma configuração de divisão de túnel.

Para obter orientação adicional sobre como configurar e validar a preparação da rede de configuração de divisão de túnel para equipes, consulte Preparação da [rede](https://docs.microsoft.com/MicrosoftTeams/prepare-network) .

> [!NOTE]
>   Devido ao volume total de soluções de acesso remoto disponíveis no mercado, este documento não pode fornecer detalhes específicos do fornecedor, diretrizes gerais apenas para o que devem ser configuradas em soluções de acesso remoto.


<table>
<tr><td>![](media/audio_conferencing_image7.png)<br/>Pontos de decisão</td><td><ul><li>Decida implementar a configuração de divisão de túnel.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Próximos passos</td><td><ul><li>Implementar a configuração de divisão de túnel.</li><li>Testar e validar a configuração de divisão de túnel.</li></ul></td></tr>
</table>


### <a name="document-split-tunnel-configuration-validation-test-results"></a>Resultados de testes de validação de configuração de divisão de túnel de documento

Depois de concluir teste de configuração de divisão de túnel para sites no escopo, crie um relatório que resume os resultados do teste e apresentá-lo durante a próxima revisão do Comitê de orientação.

#### <a name="site-a-split-tunnel-configuration-validation-testing-summary-report"></a>Site r: validação da configuração de divisão de túnel testando o relatório de resumo

> [!TIP]
>   Abaixo é um exemplo de modelo de relatório de resumo que você possa examinar durante a próxima reunião comitê de direcionamento ao decidir quando para onboard sistema telefônico com planos de chamar serviços na fase piloto de teste.

**Validação da configuração de divisão de túnel**

**Resumo dos resultados**:&nbsp;&nbsp;&nbsp;& #9744; Passe&nbsp; &nbsp; &nbsp; & #9744; Parcial&nbsp; &nbsp; &nbsp; & #9744; Falhar

<table>
<tr><th colspan="2">Destaques de teste </th></tr>
<tr><td>TBD</td><td>TBD</td></tr>
<tr><th colspan="2">Testando pontos menos importantes  </th></tr>  
<tr><td>**Problema**: TBD</td><td>**Remediação:** TBD</td></tr>
<tr><th colspan="2">Bloqueadores identificados </td></tr>
<tr><td>**Bloqueador**: TBD</td><td>**Correção**: TBD</td></tr>
</table>


> [!TIP]
> Para facilitar a discussão adicional durante a revisão final comitê de orientação, você pode usar atualizado [matriz de resultados de testes](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_21) de [MyAdvisor](https://myadvisor.fasttrack.microsoft.com/) para documentar e destacar áreas adicionais que exigem remediação.


<table>
<tr><td>![](media/audio_conferencing_image7.png)<br/>Pontos de decisão</td><td><ul><li>Avalie a divisão de túnel os resultados dos testes para garantir que o tráfego de equipes em tempo real está sendo excluído da solução de acesso remoto.</li></ol></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Próximos passos</td><td><ul><li>Documente os resultados de testes de conectividade de divisão de túnel no modelo de resultado do plano de teste fornecido.</li><li>Execute planos de escalação e correção para resolver problemas em que o roteamento apropriado talvez não exista para dar suporte a mídia de equipes em uma configuração de divisão de túnel.</li><li>Agende uma reunião comitê de orientação para revisar o resumo de resultados de teste.</li><li>Presente teste resumo de resultados para o Comitê de orientação para identificar quaisquer áreas que exigem remediação.</li></ul></td></tr>
</table>


<a name="execute-network-connectivity-and-performance-validation-by-using-the-network-assessment-tool-from-microsoft"></a>Executar a validação de conectividade e desempenho de rede, usando a ferramenta de avaliação de rede da Microsoft
-----------------------------------------------------------------------------------------------------------

A ferramenta de avaliação de rede da Microsoft realiza testes de conectividade e simulação de tráfego por streaming simulados pacotes de áudio, para um período predefinido e o número de iterações, para o site mais próximo de borda que fornece conectividade com o serviço de equipes. Um objetivo deste teste é avaliar métricas de desempenho de rede para a porcentagem de reordenar pacotes de cada chamada simulada, latência de ida e volta, tremulação e perda de pacotes. Além disso, o teste valida que a conectividade apropriada é permitida entre interno e elementos de rede para todos os pontos de ingresso de borda que oferecem suporte à conectividade aos serviços de equipes de borda.

Para obter orientação adicional sobre como confirmar e avaliar a preparação da rede de equipes para sites designados nesse escopo, consulte Preparação da [rede](https://docs.microsoft.com/MicrosoftTeams/prepare-network) .

> [!TIP]
>   Para concluir a análise de preparação de rede e preparação para sites no escopo, designe um líder para cada site que pode auxiliar com os esforços de avaliação de prontidão de rede.



<table>
<tr><td>![](media/audio_conferencing_image7.png)<br/>Pontos de decisão</td><td><ul><li>Decida a avaliação da rede e o perfil de teste de conectividade para sites no escopo.</li><li>Requisitos de arquivo de configuração de avaliação de rede para sites no escopo de decidir.</li></ol></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Próximos passos</td><td><ul><li>Configure requisitos de arquivo de configuração de avaliação de rede para sites no escopo.</li><li>Execute validação de desempenho e conectividade de rede para sites no escopo.</li></ul></td></tr>
</table>



### <a name="document-network-connectivity-and-performance-validation-test-results"></a>Documente os resultados de testes de validação de conectividade e desempenho de rede

Depois de concluir todos os conectividade de rede e teste de desempenho para os sites no escopo, crie um relatório que resume os resultados do teste e apresentá-lo durante a próxima revisão do Comitê de orientação.

#### <a name="site-a-network-connectivity-and-performance-summary-report"></a>Site r: relatório de resumo de desempenho e conectividade de rede

> [!TIP]
> Abaixo é um exemplo rede conectividade e desempenho resumo modelo que você pode usar durante a próxima revisão do Comitê de orientação quando você estiver determinando a preparação da rede geral para sites no escopo.

**Local: Seattle [com fio inside] cliente para os resultados do Office 365**

**Resumo dos resultados**:&nbsp;&nbsp;&nbsp;& #9744; Passe&nbsp; &nbsp; &nbsp; & #9744; Parcial&nbsp; &nbsp; &nbsp; & #9744; Falhar 



| Métrica                                                        | Destino                                                                                                             | Weekday: meu horário de trabalho 9:30 AM para 11:00 AM                                                                                                                                                                                                                                                                                                 | Weekday: meu horário de trabalho 2:30 PM para 4:30 PM | Weekday: depois do expediente 10:30 PM para 12:30 AM | Final de semana: depois do expediente 9:30 AM para 11:30 AM | Final de semana: após o horário 2:30 PM para 4:30 PM |
|---------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------|-------------------------------------------|------------------------------------------|-----------------------------------------
| Latência (unidirecional)                                             | \<50 ms                                                                                                           | 40 ms                                                                                                                                                                                                                                                                                                                                     | 38 ms                                    | 41 ms                                     | 35 ms                                    | 36 ms                                   |
| Latência (tempo de ida e volta, ou tempo de resposta)                             | \<100 ms                                                                                                          | 81 ms                                                                                                                                                                                                                                                                                                                                     | 77 ms                                    | 80 ms                                     | 72 ms                                    | 70 ms                                   |
| Perda de pacote de intermitência                                             | \<10% durante qualquer intervalo de 200 ms                                                                                  | 3%                                                                                                                                                                                                                                                                                                                                        | 2%                                       | 2%                                        | % de 0.2                                     | 0,1%                                    |
| Perda de pacote                                                   | \<1% durante qualquer intervalo de 15 segundos                                                                                   | % de 0.4                                                                                                                                                                                                                                                                                                                                      | % de 0,3                                     | % de 0,3                                      | 0,1%                                     | 0%                                      |
| Tremulação de entre chegada de pacotes                                   | \<30 ms durante qualquer intervalo de 15 segundos                                                                                | 12 ms                                                                                                                                                                                                                                                                                                                                     | 11 ms                                    | 13 ms                                     | 5 ms                                     | 5 ms                                    |
| Novo pedido de pacotes                                                | \<% de 0,05 pacotes de fora de ordem                                                                                      | 0%                                                                                                                                                                                                                                                                                                                                        | 0%                                       | 0%                                        | 0%                                       | 0%                                      |



<table>
<tr><th colspan="2">Destaques de teste </th></tr>
<tr><td>TBD</td><td>TBD</td></tr>
<tr><th colspan="2">Testando pontos menos importantes  </th></tr> 
<tr><td>**Problema**: alta latência</td><td>**Remediação:** Investigue o roteamento de pacotes e implementar a rota ideal.</td></tr>
<tr><td>**Problema**: o tempo de ida e volta de double a latência não é</td><td>**Remediação:** Investigar um problema de configuração de firewall ou roteador possível. Investigar os caminhos de tráfego.</td></tr>
<tr><td>**Problema**: alta perda de pacotes </td><td>**Remediação:** Verifique se que a largura de banda suficiente tenha sido alocada por meio do Planejador de rede. </td></tr>
<tr><td>**Problema**: tremulação alta </td><td> **Remediação:** Investigue se os valores DSCP (ponto) do código de serviços diferenciados corretas estão sendo usados. </td></tr>
<tr><td>**Problema**: alta perda de pacotes </td><td>**Remediação:** Investigue perda de pacotes. </td></tr>
<tr><td>**Problema**: reordenar pacotes alta </td><td>**Remediação:** Investigue queueing roteador e largura de banda. </td></tr>
<tr><th colspan="2">Bloqueadores identificados </td></tr>
<tr><td>**Bloqueador**: TBD</td><td>**Correção**: TBD</td></tr>
</table>

 


<table>
<tr><td>![](media/audio_conferencing_image7.png)<br/>Pontos de decisão</td><td><ul><li>Avalie avaliação da rede e os resultados para garantir que você atende aos requisitos descritos em [desempenho de conectividade de rede e qualidade de mídia](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance) para o segmento de borda e segmentos de cliente dos testes de conectividade.</li><li>Você avaliou os recursos de rede para dar suporte a mídia em tempo real para todos os sites no escopo?</li><li> Se sua rede ainda não foi avaliada corretamente ou se você sabe que ele não oferece suporte a mídia em tempo real, você desativará vídeo e recursos de compartilhamento de tela para reduzir a rede afetam e aprimoram a experiência de equipes para usuários?</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Próximos passos</td><td><ul><li>Desempenho da rede e os resultados do teste de conectividade do documento.</li><li>Execute planos de escalação e correção para resolver problemas com sites onde não há largura de banda suficiente ou não sejam atendidos os requisitos de desempenho e conectividade de rede.</li><li>Agende uma reunião comitê de orientação para revisar o resumo de resultados de teste.</li><li>Presente teste resumo de resultados para o Comitê de orientação para identificar quaisquer áreas que exigem remediação.</li></ul></td></tr>
</table>


<a name="execute-subscriber-number-port-validation"></a>Execute validação assinante do número de porta
-----------------------------------------

Se você vai precisar transferir números como parte do fornecimento de recursos de chamada de entrada/saída no sistema telefônico com serviços de planos de chamar suportados por equipes, você deve realizar uma porta parcial para um número de serviço. Isso ajudará a validar as expectativas, requisitos e linha do tempo razoável à medida que você concluir a preparação de sua implantação do sistema telefônico com planos de chamar os serviços em seu ambiente de produção.

Para concluir uma porta parcial de um número de assinante do seu provedor de serviços PSTN atual para equipes, percorra as etapas descritas abaixo.

#### <a name="step-1"></a>Etapa 1

Identifique o número de teste que você gostaria de porta para o Office 365, como um número de usuário pode ser atribuído (número de telefone do assinante) sejam atendidas por meio do sistema de telefone com planos de chamar o serviço no equipes.

> [!IMPORTANT]
>Ao planejar seu teste portabilidade numérica, certifique-se de revisar as últimas diretrizes para solicitações de portabilidade números em [Perguntas comuns sobre o número de porta](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transferring-phone-numbers-common-questions).

#### <a name="step-2"></a>Etapa 2

Identificar e documentar todas as informações de conta (incluindo o nome usado para a conta específica) para a operadora atual do número de teste que você vai ser portando.
Normalmente, você pode encontrar as informações que você precisará no bill mais recente ou faturas do seu provedor de serviço atual.

> [!TIP]
>   Você pode transferir ou números de telefone de transferência dentro de todas as atualmente suportadas países/regiões; No entanto, a maneira como você envia uma solicitação de pedido de porta pode ser diferentes dependendo do país/região onde os números de telefone são originados de. Para obter a lista mais recente dos países/regiões atualmente com suporte, consulte [países e a disponibilidade da região para conferência de áudio e planos de chamada](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).

>   Para obter informações adicionais sobre como transferir números de telefone para o sistema telefônico com planos de chamar — juntamente com restrições possíveis — consulte [transferir os números de telefone para o Office 365](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365) e [ligação gratuita discando restrições no Office 365](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/toll-free-dialing-limitations-and-restrictions.).

#### <a name="step-3"></a>Etapa 3

Baixe e criar uma letra de autorização (LOA) para seu país/região que é baseado em "serviço de número" como o tipo de portabilidade number.

>[!NOTE]
>   Porque os formatos LOA podem diferir por tipo de número, região ou país (que é geográfica versus não geográfica ou número de usuário versus serviço ou número de chamada gratuito), verificar se você estiver usando o modelo LOA correto para o seu tipo de cenário específico. Consulte [baixar uma letra de autorização (LOA)](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/download-a-letter-of-authorization-loa) para obter mais informações sobre como escolher o LOA ou ir diretamente para a [página de download](https://www.microsoft.com/download/details.aspx?id=49167).

>[!NOTE]
> **Estados Unidos somente**<br/>
>   Porque só podemos estiver portar um número de serviço para este teste, certifique-se de selecionar os campos apropriados no LOA, conforme mostrado abaixo:

![Como muitos números de telefone serão transferidos? Resposta: eu estou transferindo apenas alguns dos Meus números de minha operadora atual.] (media/onboarding-test-plan-image1.png "Como muitos números de telefone serão transferidos? Resposta: eu estou transferindo apenas alguns dos Meus números de minha operadora atual.")

![Qual tipo de números de telefone serão você ser transferindo? Resposta: eu estou transferindo números de telefone do serviço de voz como para atendedores automáticos ou pontes de conferência.] (media/onboarding-test-plan-image2.png "Qual tipo de números de telefone serão você ser transferindo? Resposta: eu estou transferindo números de telefone do serviço de voz como para atendedores automáticos ou pontes de conferência.")

>[!IMPORTANT]
>   Quando você manualmente a porta números de telefone usando uma LOA, certifique-se de que selecionar o tipo de número de telefone correto. É necessário enviar pedidos de portabilidade separados para cada tipo de número de telefone que você queira transferir.<br/><br/>
>   Porque queremos testar o número da porta processo usando um número de telefone associado com o mesmo número de telefone faturamento (BTN), você precisará garantir que o número de telefone de faturamento *não* está incluído com o número de telefone específico que está sendo migrado.

#### <a name="step-4"></a>Etapa 4

No portal de administração do inquilino, vá para a guia **suporte** e criar e enviar uma solicitação de serviço. Anexe o arquivo LOA concluído para agendar o número de telefone associado ao seu provedor de serviços atual para a migração. Para escolher o método de solicitação de serviço mais apropriado para o tamanho do seu locatário, consulte [manualmente enviar uma solicitação de serviço personalizado](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/manually-submit-a-custom-service-request).

Depois que a solicitação de suporte é recebida, Microsoft Support seguirão com base em que o método de comunicação que você tenha escolhido e orientar você do status e as próximas etapas para concluir o processo de portabilidade número.

#### <a name="step-5"></a>Etapa 5

Depois que o número for confirmado como tendo sido migradas como um novo número de telefone do assinante no Office 365, atribua o número para o sistema telefônico com planos de chamar o serviço indo para o portal de administração de locatário \> **Skype para Business Admin Center** \> ** Voz**. Na guia **Números de telefone** , atribua o novo número de serviço para o sistema telefônico com planos de chamar o serviço.

> [!TIP]
>   Embora essa tarefa atribui um novo número de serviço para o sistema telefônico com planos de chamada, no momento da redação deste artigo, a administração desta tarefa for concluída, usando o Skype para centro de administração de negócios.

#### <a name="step-6"></a>Etapa 6

Agora que você atribuiu o número de porta do assinante, entrar com um cliente de equipes que o usuário e discar um número de 10 dígitos externo por meio da PSTN. Depois que você coloca a chamada, confirme que a chamada foi conectada e se a ID de chamador exibido corresponde o número de telefone do assinante que você duas portas.

#### <a name="step-7"></a>Etapa 7

A partir de um número PSTN externo, fazer uma chamada para o número de telefone do assinante com duas portas para o Office 365 e verifique se que a chamada for recebida de entrada e conectadas via o cliente de equipes.



<table>
<tr><td>![](media/audio_conferencing_image7.png)<br/>Pontos de decisão</td><td><ul><li>Decida quais números de assinante domésticas, você precisará porta, por país/região.</li><li>Decida qual modelo de LOA que você usará.</li><li>Determinar se a sua operadora atual (perder operadora) permite fragmentação de número de telefone (ou seja, permite pedidos de porta parcial).</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Próximos passos</td><td><ul><li>Coletar as informações necessárias e prepare as LOAs.</li><li>Baixar e concluir os modelos LOA que você precisa.</li><li>Envie uma solicitação de portabilidade de número de telefone do assinante.</li><li>Executar o teste de validação para os números de porta, atribuindo-los para o sistema telefônico com planos de chamar o serviço para o acesso de discagem e confirmar que funcionem, conforme descrito nas etapas 6 e 7 anteriormente nesta seção.</li></ul></td></tr>
</table>


### <a name="document-service-number-porting-test-results"></a>Número de serviço portando resultados do teste de documentos

Depois de concluir todos os testes de número de telefone do assinante, crie um relatório que resume os resultados do teste para apresentar durante a próxima revisão do Comitê de orientação.

#### <a name="site-a-number-porting-test-summary-report"></a>Número do site r: portando relatório de resumo de teste

> [!TIP]
>   Abaixo é um modelo de relatório de resumo de teste de exemplo que você pode usar para revisão durante a próxima reunião comitê de direcionamento ao decidir quando para onboard sistema telefônico com planos de chamar serviços na fase piloto.

**Número de serviço portando**

**Resumo dos resultados**:&nbsp;&nbsp;&nbsp;& #9744; Passe&nbsp; &nbsp; &nbsp; & #9744; Parcial&nbsp; &nbsp; &nbsp; & #9744; Falhar 

<table>
<tr><th colspan="2">Destaques de teste </th></tr>
<tr><td>TBD</td><td>TBD</td></tr>
<tr><th colspan="2">Testando pontos menos importantes  </th></tr>  
<tr><td>**Problema**: TBD</td><td>**Remediação:** TBD</td></tr>
<tr><th colspan="2">Bloqueadores identificados </td></tr>
<tr><td>**Bloqueador**: TBD</td><td>**Correção**: TBD</td></tr>
</table>


> [!TIP]
>   Para facilitar a discussão adicional durante a revisão final comitê de orientação, você pode usar atualizados da [matriz de resultados de teste](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_21) fornecido pelo [MyAdvisor](https://myadvisor.fasttrack.microsoft.com/) documentar e destacar áreas de teste adicionais que exigem remediação.


<table>
<tr><td>![](media/audio_conferencing_image7.png)<br/>Pontos de decisão</td><td><ul><li>Avalie se enviados para a migração de multiusuários foram transferidos com êxito para o sistema telefônico com planos de chamar o serviço..</li><li>Avalie se você pudesse atribuir o número de porta do serviço para o sistema telefônico com planos de chamar o serviço.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Próximos passos</td><td><ul><li>Documente o seu número portando resultados do teste.</li><li>Execute planos de escalação e correção para resolver problemas que você enfrentou com o processo de portabilidade número, se houver alguma.</li><li>Agende uma reunião comitê de orientação para revisar o resumo de resultados de teste.</li><li>Apresente os resultados do resumo de teste para o Comitê de orientação para identificar quaisquer áreas que exigem remediação.</li></ul></td></tr>
</table>


<a name="execute-your-test-plan-for-phone-system-with-calling-plans"></a>Executar o seu plano de teste para o sistema telefônico com planos de chamada
----------------------------------------------------------

Agora que você definiu seu plano de teste, a próxima etapa é para percorrer os casos de teste, concentrando-se sobre como avaliar o sistema telefônico com planos de chamar administração e experiência de usuário recursos no escopo. Antes de realmente testando começa, verifique se os pré-requisitos de testes listados abaixo estão no lugar.

### <a name="phone-system-with-calling-plans-testing-prerequisites"></a>Sistema telefônico com chamar planos de teste de pré-requisitos

-   Casos de uso de negócios tiverem sido definidos para o sistema telefônico com planos de chamar o serviço.

-   Os principais participantes foram identificados.

-   O licenciamento necessário para o sistema telefônico com serviços de planos de chamada está disponível e foi atribuído ao grupo de usuários no escopo.

-   A lista de sites organizacionais e de grupos de usuários no escopo foram identificados.

-   [Créditos de comunicações](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits) (se necessário) tiverem sido configurados para sua organização.

-   O sistema telefônico com configurações de planos de chamada foram identificados e configurados.

-   Configurações que oferecem suporte ao sistema telefônico com planos de chamada foram identificadas, configuradas e aplicadas para o grupo de usuários no escopo de plano de discagem de locatário.

-   O sistema telefônico com políticas de planos de chamada foram identificados e configurados para o grupo de usuários no escopo.

-   O sistema telefônico com planos de chamar os requisitos de conformidade foram identificados e configurados para o grupo de usuários no escopo.

### <a name="document-phone-system-with-calling-plans-test-case-passfail-status"></a>Sistema de telefone de documentos com planos de chamar status de aprovação/reprovação do caso de teste

À medida que os casos de teste são avaliados para equipes administrativas e recursos de sistema de telefone do usuário no escopo, controle os resultados de cada caso de teste para refletir o status parcial/aprovação/reprovação, juntamente com a identificação do defeito atribuída no caso de surgirem problemas imprevisíveis.

#### <a name="phone-system-with-calling-plans-test-case-status"></a>Sistema telefônico com planos de chamar status do caso de teste

> [!TIP]
>   Abaixo é um modelo de status do caso de teste de exemplo que você pode usar para resultados de testes de documento para revisão durante a próxima reunião comitê de direcionamento ao decidir quando para onboard sistema telefônico com planos de chamar serviços na fase piloto.

| Sistema de Telefonia com Planos de Chamadas          |                              |                                                                                            |                           |                                                                            |
|------------------------------------------|------------------------------|--------------------------------------------------------------------------------------------|---------------------------|----------------------------------------------------------------------------|
| ID do caso de teste                             | Título do caso de teste              | Descrição do caso de teste                                                                      | Resumo de resultados de caso de teste | ID de defeito atribuídos (se aplicável)                                         |
| 1                                        | Fazendo chamadas PSTN de saída. | Realiza uma chamada de saída, discando um número de 10 dígitos nacionais.                              |    & #9744; Passar<br/>& #9744; Parcial<br/> & #9744; Falhar                   | Quando um usuário insere um número de quatro dígitos, a chamada feita para o PSTN falha. |



<table>
<tr><td>![](media/audio_conferencing_image7.png)<br/>Pontos de decisão</td><td><ul><li>Avalie o status de aprovação/reprovação do caso de teste de alto nível pelo site para o sistema telefônico com planos de chamar os recursos no escopo.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Próximos passos</td><td><ul><li>Os resultados de status do caso de teste para todos os casos de teste concluídos no escopo do documento.</li><li>Agende uma reunião comitê de orientação para revisar o resumo de resultados de teste.</li><li>Apresentar os resultados de status do caso de teste para o Comitê de orientação para identificar quaisquer áreas que exigem remediação.</li></ul></td></tr>
</table>


### <a name="document-phone-system-with-calling-plans-testing-result-summary"></a>Sistema de telefone do documento com chamar planos de resumo de resultados de teste

Após todos os casos de teste com suporte para o sistema telefônico com planos de chamar os recursos no escopo tenham sido concluídas por site, documentar os resultados para revisar durante uma reunião comitê de direcionamento ao decidir quando ativar o sistema telefônico com planos de chamar os serviços do piloto fase.

#### <a name="site-a-phone-system-with-calling-plans-test-case-summary-report"></a>Site r: sistema de telefone com o relatório de resumo de caso de teste planos de chamada:

> [!TIP]
>   Abaixo é um modelo de relatório de resumo de teste de exemplo que você possa examinar durante a próxima reunião comitê de direcionamento ao decidir quando para onboard sistema telefônico com planos de chamar serviços na fase piloto.


**Sistema telefônico de equipes com a chamada de planos**

**Resumo dos resultados**:&nbsp;&nbsp;&nbsp;& #9744; Passe&nbsp; &nbsp; &nbsp; & #9744; Parcial&nbsp; &nbsp; &nbsp; & #9744; Falhar 

<table>
<tr><th colspan="2">Destaques de teste </th></tr>
<tr><td>TBD</td><td>TBD</td></tr>
<tr><th colspan="2">Testando pontos menos importantes  </th></tr>  
<tr><td>**Problema**: TBD</td><td>**Remediação:** TBD</td></tr>
<tr><th colspan="2">Bloqueadores identificados </td></tr>
<tr><td>**Bloqueador**: TBD</td><td>**Correção**: TBD</td></tr>
</table>


> [!TIP]
>   Para facilitar a discussão adicional durante a revisão final comitê de orientação, você pode usar o atualizado [matriz de resultados de testes](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_21) fornecidos pelo [MyAdvisor](https://myadvisor.fasttrack.microsoft.com/) documentar e destacar áreas adicionais que exigem remediação.



<table>
<tr><td>![](media/audio_conferencing_image7.png)<br/>Pontos de decisão</td><td><ul><li>Avalie o resumo de resultados de teste de alto nível pelo site para o sistema telefônico com planos de chamar os recursos no escopo.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Próximos passos</td><td><ul><li>Documente o relatório de resumo de caso de teste depois que todos os resultados de caso de teste tenham sido concluídos.</li><li>Agende uma reunião comitê de orientação para revisar o resumo de resultados de teste.</li><li>Presente teste resumo de resultados para o Comitê de orientação para identificar quaisquer áreas que exigem remediação.</li></ul></td></tr>
</table>



<a name="present-and-report-phone-system-with-calling-plans-test-findings"></a>Apresentar e relatar o sistema telefônico com planos de chamar descobertas de teste
----------------------------------------------------------------

Afinal atividades de testes foram concluídas e quaisquer defeitos com um impacto de baixa foram resolvidos, agendar uma reunião de encerramento final com as partes interessadas testing designadas. Na reunião, endereço:

-   Resumo do status

-   Realce/pontos menos importantes

-   Lições aprendidas

-   Recomendação geral — passar para a fase piloto ou reavalie resultados do teste?

-   Resultados do teste matrix (esses devem ser totalmente documentados em um apêndice)

#### <a name="test-plan-deliverables"></a>Resultados finais de plano de teste:

> [!TIP]
>   Abaixo é um exemplo de modelo de produto que você pode usar para documentar os critérios necessários para obter aprovação e sair da fase de teste ou suspender o teste até que todos os problemas identificados forem resolvidos totalmente um plano de teste.

| Resumo do status               | Destaques/pontos menos importantes | Lições aprendidas | Recomendação de fechamento |
|------------------------------|----------------------|-----------------|------------------------|
| <ul><li>Taxa de pass caso de teste de % TBD</li><li>Todos os testes passados</li></ul> | TBD                  | TBD             | Vá para o piloto       |

-   Todos os testes passados


<table>
<tr><td>![](media/audio_conferencing_image7.png)<br/>Pontos de decisão</td><td><ul><li>Decida o status de teste resumo.</li><li>Identifique os pontos menos importantes e destaques do teste.</li><li>Identifica lições aprendidas.</li><li>Decida qual remediação permanecem de ações, se houver alguma.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Próximos passos</td><td><ul><li>Documento resumo resultados do teste para incluir:<ul><li>Resumo do status</li><li>Destaques/pontos menos importantes</li><li>Lições aprendidas</li></ul></li><li>Agende uma reunião final comitê de orientação para analisar os resultados de teste.</li><li>Resultados de teste de resumo presente durante um comitê de orientação Revise para obter aprovação final para saindo a fase de teste.</li></ul></td></tr>
</table>