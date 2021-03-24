---
title: Preparar para implantar o serviço de voz na nuvem
author: rmw2890
ms.author: Rowille
manager: serdars
audience: ITPro
ms.date: 03/18/2019
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Use listas de verificação de integração para preparar o Microsoft 365 ou o Office 365 para o Teams e configurar os principais recursos, a rede e as cargas de trabalho de voz na nuvem do Teams.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 42ded974ba5f4400bdcb5796410a8277fbed4488
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103967"
---
# <a name="prepare-my-service"></a>Preparar meu serviço

Este artigo fornece uma visão geral dos requisitos para preparar serviços de voz na nuvem para sua organização. Ao se preparar corretamente, você pode ter certeza de que está pronto para fornecer recursos de voz na nuvem para sua organização.

## <a name="onboarding-checklists-for-microsoft-teams-voice-workloads"></a>Lista de verificação de integração para cargas de trabalho de voz do Microsoft Teams

As listas de verificação a seguir orientam você pelas etapas para implementar a Audioconferência, o Sistema de Telefonia com Planos de Chamadas ("Planos de Chamadas") e os recursos de Roteamento Direto do Sistema de Telefonia ("Roteamento Direto") no Microsoft Teams.

*  [Preparar o Microsoft 365 ou o Office 365 para o Teams](onboarding-checklist-enable-office-365.md)

*  [Configurar os principais recursos do Teams](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)

*  [Preparar sua rede](prepare-network.md)

*  [Configurar cargas de trabalho de voz na nuvem no Teams](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)

*  [Configurar Roteamento Direto no Teams](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)

As tarefas e atividades nessas listas de verificação são os principais itens "a fazer" que se aplicam a cada implantação de recursos de voz na nuvem com o Teams. Você pode personalizar as listas de verificação para incluir as atividades e tarefas específicas de sua própria jornada do Teams.

>[!NOTE]
>Essa orientação se concentra exclusivamente em Planos de Chamadas, Audioconferência e Roteamento Direto. Se você for novo no Teams, revise [Visão geral do Microsoft Teams.](teams-overview.md) Para obter orientações gerais para o planejamento da implantação do Teams, comece com [Implantar chat, equipes, canais e aplicativos no Microsoft Teams.](deploy-chat-teams-channels-microsoft-teams-landing-page.md)

Use as listas de verificação fornecidas para controlar o status de cada atividade e tarefa individuais e para ter certeza de que você não ignorou nenhuma etapa crítica. Cada atividade inclui uma descrição detalhada das ações e referências necessárias a informações adicionais que você pode usar para concluir essa atividade.

Embora seja recomendável que você siga as listas de verificação em ordem, a sequência exata dependerá do escopo da sua implantação e da configuração e complexidade do seu ambiente. Eles são organizados para dar suporte a uma implantação do Teams "greenfield" (uma sem presença anterior do Skype for Business Online) ou migrar do Skype for Business Online para o Teams. Se você estiver migrando do Skype for Business Online, talvez já tenha concluído algumas dessas atividades e possa ignorá-las agora.

Quando você está integrando usuários por site, recomendamos que você use o Manual de Habilitações de Site para Voz [(Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) como um guia complementar para essas listas de verificação.

>[!NOTE]
>A maioria das configurações é comum entre o Teams e o Skype for Business Online. Você usa o Centro de Administração do Microsoft 365 e o Centro de administração do Microsoft Teams para configurar essas configurações.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Pontos de decisão</td><td><ul><li>Quem será responsável por supervisionar a conclusão das listas de verificação de integração?</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Próximas etapas</td><td><ul><li>Baixe as listas de verificação de integração.</li><li>Trabalhe os itens da lista de verificação de integração passo a passo de acordo com o plano de implantação da sua organização.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="continue-onboarding"></a>Continuar integrando

Depois de concluir essas listas de verificação, você terá adicionado recursos de voz com êxito à implantação do Teams.

Como próxima etapa, use o Manual de Reprodução de Habilitação de Site para [Voz (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) para ajudá-lo a integrar seus usuários em cada site e ajudar a garantir que você planeje e execute atividades importantes específicas do site.

-   Plano de lançamento de site por site pronto

-   Estabelecer processo de gerenciamento de serviços

-   Executar Testes e Correção

<!--ENDOFSECTION-->

## <a name="test-cloud-voice-workloads-in-teams"></a>Testar cargas de trabalho de voz na nuvem no Teams

Depois de definir e documentar seus planos de sucesso e implementação técnica de negócios de voz na nuvem do Teams como parte da fase Envision e realizar a configuração que você deseja no centro de administração, a próxima etapa é validar se as expectativas e os requisitos da sua organização são atendidos por meio do recurso, funcionalidade e usabilidade. Você deve executar essa etapa de validação antes de implantar uma implantação piloto ou final em seu ambiente de produção.

Você pode aproveitar o plano de sucesso comercial definido durante a fase Envision para servir como base para determinar as atividades, as expectativas, os casos de teste de recursos/funcionalidades e o escopo geral a ser avaliado durante a fase de teste.

## <a name="define-your-testing-approach"></a>Definir sua abordagem de teste

Em sua forma mais simples, sua abordagem de teste baseia-se na revisão dos recursos do serviço de Audioconferência, Planos de Chamadas ou Roteamento Direto e desenvolvimento de um plano de teste para verificar se seus requisitos de funcionalidade são atendidos para usuários no escopo. A seguir, um exemplo de plano de teste para a fase Onboard de uma implementação de audioconferência.


| Recurso de audioconferência para teste | Resumo de resultados | Notas adicionais |
|------------|-----------------|------------------|
| Agendar uma reunião do Teams ad hoc que contenha informações de discagem de audioconferência | Pass/Fail   | TBD |
| Use um telefone para áudio de reunião discando em uma reunião da PSTN com as informações de discagem fornecidas | Pass/Fail | TBD |
| Instrua outras pessoas a uma reunião existente discando por meio do PSTN | Pass/Fail | TBD |



| Plano de Chamadas ou Recurso de Roteamento Direto a ser testado | Resumo de resultados | Notas adicionais |
|----------------------------------------------------|-----------------|------------------|
| Fazer uma chamada PSTN discando um número PSTN       | Pass/Fail       | TBD |
| Receber uma chamada PSTN discando seu número PSTN de uma linha externa (celular, telefone fixo) | Pass/Fail | TBD|
| Transferir uma chamada PSTN de um usuário do Teams para outro | Pass/Fail | TBD |


>[!TIP]
>Para ajudar na criação de casos de teste como ponto de partida, consulte a lista de orientações do usuário disponíveis em Reuniões e chamadas [do Teams.](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings)

<!--ENDOFSECTION-->

## <a name="set-up-cloud-voice-workloads-for-teams"></a>Configurar cargas de trabalho de voz na nuvem para o Teams

Agora que você definiu sua abordagem de teste, a próxima etapa é configurar seu ambiente de serviço e usuários no escopo para recursos de voz na nuvem do Teams.

Para obter informações adicionais, consulte:

- [Planejamento técnico da Audioconferência](./cloud-voice-landing-page.md)

- [Configurar Audioconferência no Microsoft Teams](set-up-audio-conferencing-in-teams.md)

- [Planejamento Técnico do Sistema de Telefonia com Planos de Chamadas](calling-plan-landing-page.md)

- [Configurar planos de chamadas para o Skype for Business e o Microsoft Teams](/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

- [Planejar o Roteamento Direto](./direct-routing-plan.md)

- [Configurar o Roteamento Direto](./direct-routing-configure.md)

### <a name="execute-the-test-plan"></a>Executar o plano de teste

[//]: # (Editar ok? "Usuário" me parecia um pouco ambíguo.)
Depois que o ambiente do usuário e o serviço foram configurados, a última etapa de teste inclui a execução do plano de teste com foco na validação de recursos e funcionalidades. 

**Pré-requisitos e suposições de teste de audioconferência para usuários e sites no escopo:**

-   A definição de caso de uso comercial para o serviço de Audioconferência foi concluída.

-   O licenciamento necessário para Audioconferência está disponível e foi atribuído.

-   A lista de sites organizacionais e grupos de usuários foi identificada.

-   A lista de discagem de audioconferência dedicada e compartilhada em números com preferência de idioma foi identificada e configurada.

-   [Os Créditos de](what-are-communications-credits.md) Comunicações (se necessário) foram definidos para sua organização.

-   As configurações da ponte de conferência de audioconferência foram identificadas e configuradas (comprimento do PIN, notificações de entrada/saída, preferência de notificação de habilitação).

-   As políticas de conferência de locatário e as configurações do plano de discagem que suportam cenários de discagem de Audioconferência foram identificadas, configuradas e aplicadas.

-   Os requisitos de conformidade de audioconferência foram identificados e configurados.

**Planos de Chamada testando pré-requisitos e suposições para usuários e sites no escopo:**

-   A definição de caso de uso comercial para o serviço Planos de Chamada foi concluída.

-   O licenciamento necessário para Planos de Chamada está disponível e foi atribuído.

-   A lista de sites organizacionais e grupos de usuários foi identificada.

-   Os números de telefone a serem atribuídos aos usuários foram adquiridos ou portados para a Microsoft e estão disponíveis no portal do locatário.

-   [Os Créditos de](what-are-communications-credits.md) Comunicações (se necessário) foram definidos para sua organização.

-   As políticas de usuário do locatário e as configurações do plano de discagem que suportam cenários de Planos de Chamada foram identificadas, configuradas e aplicadas.

-   Os requisitos de conformidade de Planos de Chamada foram identificados e configurados.

**Pré-requisitos e suposições de teste de Roteamento Direto para usuários e sites no escopo:**

-   A definição de caso de uso comercial para o serviço de Roteamento Direto foi concluída.

-   O licenciamento necessário para Roteamento Direto está disponível e foi atribuído.

-   A lista de sites organizacionais e grupos de usuários foi identificada.

-   Um [controlador de borda de sessão certificado (SBC)](./direct-routing-plan.md#supported-session-border-controllers-sbcs) foi implantado, configurado e emparelhado com o Sistema de Telefonia.

-   A voz da empresa foi habilitada e os números de telefone foram atribuídos.

-   As políticas de roteamento de voz foram identificadas, configuradas e atribuídas.

-   O Microsoft Teams foi definido como o cliente de chamada preferencial para os usuários no escopo.
 
-   Os requisitos de conformidade de Roteamento Direto foram identificados e configurados.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Pontos de decisão</td><td><ul><li>Decida quais recursos de recurso de Audioconferência serão implantados (decisão de serviço).</li><li>Identificar os requisitos de funcionalidade do usuário para Audioconferência.</li><li>Identificar requisitos de configuração de serviço para Audioconferência.</li><br><li>Decida se os Planos de Roteamento Direto ou De Chamada serão implantados e configurados.<li>Decida quais recursos do Sistema de Telefonia serão implantados (decisão de serviço).</li><li>Identifique os requisitos de funcionalidade do usuário para Planos de Chamadas ou Roteamento Direto.</li><li>Identifique o requisito de configuração do serviço para Planos de Chamadas ou Roteamento Direto.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Próximas etapas</td><td><ul><li>Desenvolva e documente sua abordagem de plano de teste.</li><li>Prepare seu ambiente de serviço e usuários em escopo para recursos de Audioconferência.</li><li>Prepare seu ambiente de serviço e usuários no escopo para Planos de Chamadas ou Recursos de Roteamento Direto.</li><li>Execute a validação de teste para os recursos de Audioconferência que você deseja habilitar.</li><li>Execute a validação de teste para os recursos de Planos de Chamadas ou Roteamento Direto que você deseja habilitar.</li><li>Para qualquer falha de teste, confirme se sua configuração está correta, revise os artigos da comunidade e, se necessário, aumente um caso de suporte.</li></ul></td></tr>
</table>


Para obter orientações detalhadas adicionais sobre como executar testes para Audioconferência no Teams, consulte o guia de teste detalhado [para Audioconferência](./deploy-audio-conferencing-teams-landing-page.md).

Para obter orientações detalhadas adicionais sobre como executar testes para planos de chamadas no Teams, consulte o guia de teste detalhado [para o Sistema de Telefonia.](./cloud-voice-landing-page.md)

<!--ENDOFSECTION-->