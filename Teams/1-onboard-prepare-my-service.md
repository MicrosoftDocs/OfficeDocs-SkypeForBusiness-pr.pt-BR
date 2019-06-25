---
title: Preparar para implantar os serviços de voz da nuvem do Microsoft Teams
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 03/18/2019
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Use as listas de verificação integradas para preparar o Office 365 para equipes e configurar as principais funcionalidades, redes e cargas de trabalho de voz na nuvem do teams.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b29d51d2e92659b7fbae9eb86863a2e4f205a061
ms.sourcegitcommit: a388aec386b1a72b44c24d5f189a8c1cd401f706
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/24/2019
ms.locfileid: "35198544"
---
# <a name="prepare-my-service"></a>Preparar meu serviço

Este artigo apresenta uma visão geral dos requisitos para a preparação dos serviços de voz em nuvem para a sua organização. Ao preparar-se corretamente, você pode ter certeza de que está pronto para fornecer recursos de voz na nuvem para a sua organização.

## <a name="onboarding-checklists-for-microsoft-teams-voice-workloads"></a>Listas de verificação de integração para as cargas de trabalho de voz do Microsoft Teams

As listas de verificação a seguir orientam você pelas etapas para implementar a conferência de áudio, sistema telefônico com planos de chamada ("planos de chamada") e recursos de roteamento direto do sistema telefônico ("roteamento direto") no Microsoft Teams.

*  [Preparar o Office 365 para Teams](onboarding-checklist-enable-office-365.md)

*  [Configurar recursos essenciais do teams](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)

*  [Configurar a rede](onboarding-checklist-configure-networking.md)

*  [Configurar cargas de trabalho de voz na nuvem no Teams](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)

*  [Configurar o roteamento direto no Teams](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)

As tarefas e atividades nessas listas de verificação são itens principais que se aplicam a cada implantação de recursos de voz na nuvem com o Microsoft Teams. Você pode personalizar as listas de verificação para incluir as atividades e tarefas específicas à sua viagem de equipes.

>[!NOTE]
>Esta orientação se concentra exclusivamente em planos de chamada, videoconferências e encaminhamento direto. Se você não tem experiência com o Microsoft Teams, consulte [visão geral do Microsoft Teams](teams-overview.md). Para obter orientação geral para planejar a implantação de suas equipes, comece com a [implantação de chat, equipes, canais e aplicativos no Microsoft Teams](deploy-chat-teams-channels-microsoft-teams-landing-page.md).

Use as listas de verificação fornecidas para acompanhar o status de cada atividade e tarefa individual e para ter certeza de que você não ignorou nenhuma etapa crítica. Cada atividade inclui uma descrição detalhada das ações necessárias e referências a informações adicionais que você pode usar para concluir a atividade.

Embora recomendemos que você siga as listas de verificação em ordem, a sequência exata dependerá do escopo da sua implantação e da configuração e da complexidade do seu ambiente. Elas são organizadas para dar suporte a uma implantação de equipes "greenfield" (uma sem presença anterior do Skype for Business online) ou migrar do Skype for Business online para o Microsoft Teams. Se você estiver migrando do Skype for Business Online, talvez já tenha concluído algumas dessas atividades e poderá ignorá-las agora.

Quando você estiver fazendo a integração de usuários de acordo com o site, é altamente recomendável usar o guia [de habilitação do site para voz (guia estratégico)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) como um guia complementar para essas listas de verificação.

>[!NOTE]
>A maioria das configurações de configuração é comum entre o Teams e o Skype for Business online. Você usa o centro de administração do Microsoft 365 e o centro de administração do Microsoft Teams para definir essas configurações.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Pontos de decisão</td><td><ul><li>Quem será responsável por supervisionar a conclusão das listas de verificação de integração?</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Próximas etapas</td><td><ul><li>Baixe as listas de verificação de integração.</li><li>Trabalhe nos itens da lista de verificação de integração, passo a passo, de acordo com o plano de implantação da sua organização.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="continue-onboarding"></a>Continuar a integração

Depois de concluir essas listas de verificação, você terá adicionado recursos de voz com êxito à implantação do seu Teams.

Como a próxima etapa, use o [Guia do guia de capacitação de site para voz (guia estratégico)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) para ajudá-lo a integrar seus usuários em cada site e ajudar a garantir que você planeje e execute atividades importantes específicas do site.

-   Plano de site pronto para distribuição de site

-   Estabelecer processo de gerenciamento de serviços

-   Executar testes e correções

<!--ENDOFSECTION-->

## <a name="test-cloud-voice-workloads-in-teams"></a>Testar cargas de trabalho de voz na nuvem no Teams

Depois de definir e documentar seus planos de sucesso e implementação de negócios de voz na nuvem da equipe como parte da fase enVision e fazer a configuração que você deseja no centro de administração, a próxima etapa é validar que a sua organização as expectativas e os requisitos são atendidos por meio do recurso, da funcionalidade e da usabilidade. Você deve executar esta etapa de validação antes de implantar uma implantação piloto ou final em seu ambiente de produção.

Você pode aproveitar o plano de sucesso para empresas definido durante a fase do enVision para servir como base para determinar as atividades, expectativas, recursos/casos de teste de funcionalidade e escopo geral a serem avaliados durante a fase de teste.

## <a name="define-your-testing-approach"></a>Definir a abordagem de teste

Em sua forma mais simples, a abordagem de teste baseia-se na revisão dos recursos de recursos da videoconferência, dos planos de chamada ou do serviço de roteamento direto e no desenvolvimento de um plano de teste para verificar se os seus requisitos de funcionalidade são atendidos para os usuários no escopo. Veja a seguir um exemplo de plano de teste para a fase onboard de uma implementação de áudio de audioconferência.


| Recurso de conferência de áudio para testar | Resumo dos resultados | Anotações adicionais |
|------------|-----------------|------------------|
| Agendar uma reunião de equipes ad hoc que contém informações de discagem de audioconferência | Aprovado/reprovado   | A ser determinado |
| Usar um telefone para o áudio da reunião discando para uma reunião da PSTN com as informações de discagem fornecidas | Aprovado/reprovado | A ser determinado |
| Ingressar em outras pessoas em uma reunião existente discando pela PSTN | Aprovado/reprovado | A ser determinado |



| Planos de chamada ou o recurso de roteamento direto para testar | Resumo dos resultados | Anotações adicionais |
|----------------------------------------------------|-----------------|------------------|
| Fazer uma chamada PSTN discando um número PSTN       | Aprovado/reprovado       | A ser determinado |
| Receber uma chamada PSTN discando o seu número PSTN de uma linha externa (móvel, telefone fixo) | Aprovado/reprovado | A ser determinado|
| Transferir uma chamada PSTN de um usuário do teams para outro | Aprovado/reprovado | A ser determinado |


>[!TIP]
>Para ajudar a criação de casos de teste como ponto de partida, confira a lista de diretrizes do usuário disponível em [reuniões e chamadas](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings)do Microsoft Teams.

<!--ENDOFSECTION-->

## <a name="set-up-cloud-voice-workloads-for-teams"></a>Configurar cargas de trabalho de voz na nuvem para equipes

Agora que você definiu a abordagem de teste, a próxima etapa é configurar seu ambiente de serviço e os usuários em escopo para recursos de voz na nuvem do teams.

Para obter mais informações, consulte:

- [Planejamento técnico da Audioconferência](cloud-voice-deployment.md)

- [Configurar Audioconferência no Microsoft Teams](set-up-audio-conferencing-in-teams.md)

- [Planejamento técnico para o sistema telefônico com planos de chamada](calling-plan-landing-page.md)

- [Configurar planos de chamadas para o Skype for Business e o Microsoft Teams](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

- [Planejar o Roteamento Direto](https://docs.microsoft.com/microsoftteams/direct-routing-plan)

- [Configurar o Roteamento Direto](https://docs.microsoft.com/microsoftteams/direct-routing-configure)

### <a name="execute-the-test-plan"></a>Executar o plano de teste

[//]: # (Editar Ok? "Usuário" parecia um pouco ambíguo para mim.)
Após a configuração do ambiente do usuário e do serviço, a última etapa do teste inclui a execução do plano de teste com foco na validação de recursos e funcionalidades. 

**Pré-requisitos e Premissões de teste de áudio para usuários e sites em escopo:**

-   Definição de caso de uso empresarial para o serviço de audioconferência foi concluída.

-   O licenciamento necessário para a conferência de áudio está disponível e foi atribuído.

-   A lista de sites organizacionais e grupos de usuários foi identificada.

-   A lista de números de discagem de conferência de áudio dedicada e compartilhada com a preferência de idioma foi identificada e configurada.

-   [Créditos de comunicações](what-are-communications-credits.md) (se necessário) foram configurados para sua organização.

-   As configurações da ponte de conferência de áudio foram identificadas e configuradas (tamanho do pino, notificações de entrada/saída, preferência de notificação de habilitação).

-   Políticas de conferência de locatários e configurações de plano de discagem que dão suporte a cenários de discagem de conferência de áudio foram identificadas, configuradas e aplicadas.

-   Os requisitos de conformidade do Audio Conferencing foram identificados e configurados.

**Planos de chamada testando pré-requisitos e suposições para usuários e sites em escopo:**

-   Definição de caso de uso empresarial para o serviço de planos de chamada foi concluída.

-   O licenciamento necessário para planos de chamada está disponível e foi atribuído.

-   A lista de sites organizacionais e grupos de usuários foi identificada.

-   Os números de telefone a serem atribuídos aos usuários foram adquiridos ou portados para a Microsoft e estão disponíveis no portal de locatários.

-   [Créditos de comunicações](what-are-communications-credits.md) (se necessário) foram configurados para sua organização.

-   Políticas de usuário locatários e configurações de plano de discagem que dão suporte a cenários de planos de chamada foram identificadas, configuradas e aplicadas.

-   Os requisitos de conformidade dos planos de chamada foram identificados e configurados.

**Pré-requisitos e suposições de testes de roteamento direto para usuários e sites em escopo:**

-   Definição de caso de uso empresarial para o serviço de roteamento direto foi concluída.

-   O licenciamento necessário para roteamento direto está disponível e foi atribuído.

-   A lista de sites organizacionais e grupos de usuários foi identificada.

-   Um [SBC (controlador de borda de sessão) certificado (SBC)](https://docs.microsoft.com/microsoftteams/direct-routing-plan#supported-session-border-controllers-sbcs) foi implantado, configurado e emparelhado com o sistema telefônico.

-   O Enterprise Voice foi habilitado e os números de telefone foram atribuídos.

-   As políticas de roteamento de voz foram identificadas, configuradas e atribuídas.

-   O Microsoft Teams foi definido como o cliente de chamada preferencial para os usuários no escopo.
 
-   Os requisitos de conformidade de roteamento direto foram identificados e configurados.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Pontos de decisão</td><td><ul><li>Decidir quais recursos do recurso de audioconferência de áudio serão implantados (decisão do serviço).</li><li>Identifique os requisitos de funcionalidade do usuário para videoconferência.</li><li>Identifique os requisitos de configuração do serviço para videoconferência.</li><br><li>Decida se o roteamento direto ou os planos de chamada serão implantados e configurados.<li>Decida quais recursos de recursos do sistema telefônico serão implantados (decisão de serviço).</li><li>Identifique os requisitos de funcionalidade do usuário para planos de chamada ou roteamento direto.</li><li>Identifique o requisito de configuração de serviço para planos de chamadas ou roteamento direto.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Próximas etapas</td><td><ul><li>Desenvolver e documentar a abordagem do plano de teste.</li><li>Preparar o ambiente de serviço e os usuários em escopo para os recursos de videoconferência de áudio.</li><li>Preparar o ambiente de serviço e os usuários em escopo para planos de chamadas ou recursos de roteamento direto.</li><li>Execute a validação de teste para os recursos de audioconferência que você deseja habilitar.</li><li>Execute a validação de teste para os planos de chamada ou os recursos de roteamento direto que você deseja habilitar.</li><li>Para qualquer falha de teste, confirme se a configuração está correta, examine os artigos da Comunidade e, se necessário, gere um caso de suporte.</li></ul></td></tr>
</table>


Para obter orientações detalhadas adicionais sobre como executar testes de videoconferências no Microsoft Teams, consulte o [Guia de teste detalhado para videoconferências](onboarding-test-plan-for-enterprises-Audio-Conferencing.md).

Para obter orientações detalhadas adicionais sobre como executar o teste de planos de chamada no Microsoft Teams, consulte o [Guia de teste detalhado para o sistema telefônico](onboarding-test-plan-for-enterprises-Phone-System.md).

<!--ENDOFSECTION-->
