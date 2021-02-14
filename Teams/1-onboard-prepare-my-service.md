---
title: Preparar-se para implantar o serviço de voz na nuvem
author: rmw2890
ms.author: Rowille
manager: serdars
audience: ITPro
ms.date: 03/18/2019
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Use listas de verificação de integração para preparar o Microsoft 365 ou o Office 365 para Teams e configurar os principais recursos, a rede e as cargas de trabalho de voz na nuvem do Teams.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 3c805e8ff14ddb1c46f83db819c5dd8a2c305914
ms.sourcegitcommit: fa567451f8f7af6d915e33809d88f26b415db54c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2020
ms.locfileid: "44610063"
---
# <a name="prepare-my-service"></a>Preparar meu serviço

Este artigo apresenta uma visão geral dos requisitos para preparar os serviços de voz na nuvem para sua organização. Ao se preparar corretamente, você pode ter certeza de que está pronto para fornecer recursos de voz na nuvem para sua organização.

## <a name="onboarding-checklists-for-microsoft-teams-voice-workloads"></a>Listas de verificação de integração para cargas de trabalho de voz do Microsoft Teams

As listas de verificação a seguir orientam você pelas etapas de implementação de AudioConferência, Sistema de Telefonia com Planos de Chamada ("Planos de Chamada") e Roteamento Direto do Sistema telefônico ("Roteamento Direto") no Microsoft Teams.

*  [Preparar o Microsoft 365 ou o Office 365 para o Teams](onboarding-checklist-enable-office-365.md)

*  [Configurar os principais recursos do Teams](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)

*  [Preparar sua rede](prepare-network.md)

*  [Configurar cargas de trabalho de voz na nuvem no Teams](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)

*  [Configurar o Roteamento Direto no Teams](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)

As tarefas e atividades nessas listas de verificação são os principais itens "tarefas a fazer" que se aplicam a todas as implantações de recursos de voz na nuvem com o Teams. Você pode personalizar as listas de verificação para incluir as atividades e tarefas específicas de sua própria jornada do Teams.

>[!NOTE]
>Essa orientação se concentra somente em Planos de Chamada, Audioconferência e Roteamento Direto. Se você for novo no Teams, revise a [visão geral do Microsoft Teams.](teams-overview.md) Para obter orientações gerais sobre como planejar sua implantação do Teams, comece com [Implantar chat, equipes, canais e aplicativos no Microsoft Teams.](deploy-chat-teams-channels-microsoft-teams-landing-page.md)

Use as listas de verificação fornecidas para controlar o status de cada atividade e tarefa individual e para garantir que você não tenha ignorado as etapas críticas. Cada atividade inclui uma descrição detalhada das ações necessárias e referências a informações adicionais que você pode usar para concluir essa atividade.

Embora seja recomendável que você siga as listas de verificação em ordem, a sequência exata dependerá do escopo da sua implantação e da configuração e complexidade do seu ambiente. Eles são organizados para dar suporte a uma implantação do Teams "greenfield" (sem presença anterior do Skype for Business Online) ou migrando do Skype for Business Online para o Teams. Se estiver migrando do Skype for Business Online, talvez você já tenha concluído algumas dessas atividades e possa ignorá-las agora.

Quando você está integrando usuários por site, é altamente recomendável usar o Manual de Habilitação de Site para Voz [(Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) como um guia complementar para essas listas de verificação.

>[!NOTE]
>A maioria das configurações é comum entre o Teams e o Skype for Business Online. Use o Centro de Administração do Microsoft 365 e o Centro de administração do Microsoft Teams para configurar essas configurações.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Pontos de decisão</td><td><ul><li>Quem será responsável por supervisionar a conclusão das listas de verificação de integração?</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Próximas etapas</td><td><ul><li>Baixe as listas de verificação de integração.</li><li>Trabalhe passo a passo nos itens da lista de verificação de integração de acordo com o plano de implantação da sua organização.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="continue-onboarding"></a>Continuar integração

Depois de concluir essas listas de verificação, você terá adicionado recursos de voz com êxito à sua implantação do Teams.

Como próxima etapa, use o Manual de Habilitação de Site para Voz [(Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) para ajudá-lo a integrar seus usuários em cada site e ajudar a garantir que você planeje e execute atividades importantes específicas do site.

-   Plano de Lançamento do Site Pronto por Site

-   Estabeleça o Processo de Gerenciamento de Serviços

-   Executar Teste e Correção

<!--ENDOFSECTION-->

## <a name="test-cloud-voice-workloads-in-teams"></a>Testar cargas de trabalho de voz na nuvem no Teams

Depois de definir e documentar o sucesso de negócios na nuvem do Teams e os planos de implementação técnica como parte da fase Previsão e realizar a configuração que você deseja no centro de administração, a próxima etapa é validar se as expectativas e os requisitos da sua organização são atendidos por meio de recursos, funcionalidades e usabilidade. Você deve executar esta etapa de validação antes de implantar uma implantação piloto ou final em seu ambiente de produção.

Você pode aproveitar o plano de sucesso comercial definido durante a fase Previsão para servir de base para determinar as atividades, as expectativas, os casos de teste de recursos/funcionalidades e o escopo geral a ser avaliado durante a fase de teste.

## <a name="define-your-testing-approach"></a>Definir sua abordagem de teste

Em sua forma mais simples, sua abordagem de teste baseia-se na sua análise dos recursos de recursos da Audioconferência, planos de chamada ou serviço roteamento direto e desenvolvimento de um plano de teste para verificar se seus requisitos de funcionalidade são atendidos para os usuários no escopo. A seguir, um plano de teste de exemplo para a fase De integração de uma implementação de audioconferência.


| Recurso de audioconferência para teste | Resumo dos resultados | Anotações adicionais |
|------------|-----------------|------------------|
| Agendar uma reunião ad hoc do Teams que contenha informações de discagem de audioconferência | Aprovado/Reprovado   | Tbd |
| Usar um telefone para o áudio da reunião discando para uma reunião do PSTN com as informações de discagem fornecidas | Aprovado/Reprovado | Tbd |
| Ingressar em outras pessoas em uma reunião existente discando por meio do PSTN | Aprovado/Reprovado | Tbd |



| Recurso Planos de Chamada ou Roteamento Direto para teste | Resumo dos resultados | Anotações adicionais |
|----------------------------------------------------|-----------------|------------------|
| Fazer uma chamada PSTN discando um número PSTN       | Aprovado/Reprovado       | Tbd |
| Receba uma chamada PSTN discando seu número PSTN de uma linha externa (celular, telefone fixo) | Aprovado/Reprovado | Tbd|
| Transferir uma chamada PSTN de um usuário do Teams para outro | Aprovado/Reprovado | Tbd |


>[!TIP]
>Para ajudar na criação de casos de teste como ponto de partida, consulte a lista de orientações do usuário disponíveis em Reuniões e chamadas [do Teams.](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings)

<!--ENDOFSECTION-->

## <a name="set-up-cloud-voice-workloads-for-teams"></a>Configurar cargas de trabalho de voz na nuvem para o Teams

Agora que você definiu sua abordagem de teste, a próxima etapa é configurar o ambiente de serviço e os usuários no escopo dos recursos de voz na nuvem do Teams.

Para obter informações adicionais, consulte:

- [Planejamento técnico da Audioconferência](cloud-voice-deployment.md)

- [Configurar Audioconferência no Microsoft Teams](set-up-audio-conferencing-in-teams.md)

- [Planejamento Técnico do Sistema de Telefonia com Planos de Chamada](calling-plan-landing-page.md)

- [Configurar planos de chamada para o Skype for Business e o Microsoft Teams](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

- [Planejar o Roteamento Direto](https://docs.microsoft.com/microsoftteams/direct-routing-plan)

- [Configurar o Roteamento Direto](https://docs.microsoft.com/microsoftteams/direct-routing-configure)

### <a name="execute-the-test-plan"></a>Executar o plano de teste

[//]: # (Editar ok? "Usuário" parecia um pouco ambíguo para mim.)
Depois que o ambiente do usuário e o serviço foram configurados, a última etapa de teste inclui a execução do plano de teste com foco na validação de recursos e funcionalidades. 

**Pré-requisitos e suposições de teste de audioconferência para usuários e sites no escopo:**

-   A definição de caso de uso comercial para o serviço de Audioconferência foi concluída.

-   O licenciamento necessário para Audioconferência está disponível e foi atribuído.

-   A lista de sites organizacionais e grupos de usuários foi identificada.

-   A lista de discagem de discagem de audioconferência dedicada e compartilhada com a preferência de idioma foi identificada e configurada.

-   [Os Créditos de](what-are-communications-credits.md) Comunicação (se necessário) foram definidos para sua organização.

-   As configurações da ponte de conferência de audioconferência foram identificadas e configuradas (tamanho do PIN, notificações de entrada/saída, preferência de notificação de habilitação).

-   As políticas de conferência de locatário e as configurações do plano de discagem que suportam cenários de discagem de AudioConferência foram identificadas, configuradas e aplicadas.

-   Os requisitos de conformidade de audioconferência foram identificados e configurados.

**Pré-requisitos e suposições de teste de Planos de Chamada para usuários e sites no escopo:**

-   A definição de caso de uso comercial para o serviço Planos de Chamada foi concluída.

-   O licenciamento necessário para Planos de Chamada está disponível e foi atribuído.

-   A lista de sites organizacionais e grupos de usuários foi identificada.

-   Os números de telefone a serem atribuídos aos usuários foram adquiridos ou portados para a Microsoft e estão disponíveis no portal do locatário.

-   [Os Créditos de](what-are-communications-credits.md) Comunicação (se necessário) foram definidos para sua organização.

-   As políticas de usuário do locatário e as configurações do plano de discagem que suportam cenários de Planos de Chamada foram identificadas, configuradas e aplicadas.

-   Os requisitos de conformidade dos Planos de Chamada foram identificados e configurados.

**Pré-requisitos e suposições de teste de roteamento direto para usuários e sites no escopo:**

-   A definição de caso de uso comercial para o serviço roteamento direto foi concluída.

-   O licenciamento necessário para o Roteamento Direto está disponível e foi atribuído.

-   A lista de sites organizacionais e grupos de usuários foi identificada.

-   Um [SBC (controlador de](https://docs.microsoft.com/microsoftteams/direct-routing-plan#supported-session-border-controllers-sbcs) borda de sessão) certificado foi implantado, configurado e emparelhado com o Sistema de Telefonia.

-   A voz corporativa foi habilitada e os números de telefone foram atribuídos.

-   As políticas de roteamento de voz foram identificadas, configuradas e atribuídas.

-   O Microsoft Teams foi definido como o cliente de chamada preferencial para os usuários no escopo.
 
-   Os requisitos de conformidade do Roteamento Direto foram identificados e configurados.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Pontos de decisão</td><td><ul><li>Decida quais recursos de recurso de Audioconferência serão implantados (decisão de serviço).</li><li>Identifique os requisitos de funcionalidade do usuário para AudioConferência.</li><li>Identifique os requisitos de configuração de serviço para Audioconferência.</li><br><li>Decida se os Planos de Roteamento Direto ou Chamada serão implantados e configurados.<li>Decida quais recursos do Sistema de Telefonia serão implantados (decisão de serviço).</li><li>Identifique os requisitos de funcionalidade do usuário para Planos de Chamada ou Roteamento Direto.</li><li>Identifique o requisito de configuração de serviço para Planos de Chamada ou Roteamento Direto.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Próximas etapas</td><td><ul><li>Desenvolva e documente a abordagem do plano de teste.</li><li>Prepare seu ambiente de serviço e os usuários no escopo dos recursos de Audioconferência.</li><li>Prepare seu ambiente de serviço e os usuários no escopo para planos de chamada ou recursos de Roteamento Direto.</li><li>Execute a validação de teste para os recursos de Audioconferência que você deseja habilitar.</li><li>Execute a validação de teste para os planos de chamada ou os recursos de Roteamento Direto que você deseja habilitar.</li><li>Para quaisquer falhas de teste, confirme se sua configuração está correta, revise os artigos da comunidade e, se necessário, levante um caso de suporte.</li></ul></td></tr>
</table>


Para obter orientações detalhadas adicionais sobre como executar testes de Audioconferência no Teams, consulte o guia de teste detalhado [para Audioconferência.](onboarding-test-plan-for-enterprises-Audio-Conferencing.md)

Para obter orientações detalhadas adicionais sobre como executar testes para Planos de Chamada no Teams, consulte o guia de teste detalhado [do Sistema de Telefonia.](onboarding-test-plan-for-enterprises-Phone-System.md)

<!--ENDOFSECTION-->
