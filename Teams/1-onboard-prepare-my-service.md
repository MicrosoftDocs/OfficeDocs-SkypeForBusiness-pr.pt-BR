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
description: Use as listas de verificação de inclusão preparar o Office 365 para equipes e configurar recursos principais de equipes, rede e cargas de trabalho de voz na nuvem.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 886fb0d851112fbb76ca20aeb6b4c1b35e736757
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32241366"
---
# <a name="prepare-my-service"></a>Preparar meu serviço

Este artigo fornece uma visão geral dos requisitos de preparação dos serviços de voz para sua organização de nuvem. Ao preparar-se adequadamente, você pode ser que você esteja pronto para fornecer recursos de voz para sua organização de nuvem.

## <a name="onboarding-checklists-for-microsoft-teams-voice-workloads"></a>Listas de verificação de inclusão for Microsoft Teams cargas de trabalho de voz

As listas de verificação a seguintes orientam você pelas etapas de implementação da conferência de áudio, o sistema telefônico com chamar planos ("chamar planos") e recursos do sistema direto roteamento de telefone ("direto roteamento") no Microsoft Teams.

*  [Preparar o Office 365 para equipes](onboarding-checklist-enable-office-365.md)

*  [Configurar os principais recursos de equipes](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)

*  [Configurar a rede](onboarding-checklist-configure-networking.md)

*  [Configurar as cargas de trabalho de voz de nuvem em equipes](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)

*  [Configurar o roteamento direta em equipes](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)

As tarefas e atividades nestas listas de verificação são core "tarefas pendentes" itens que se aplicam a todas as implantações de recursos de voz com as equipes de nuvem. Você pode personalizar as listas de verificação para incluir as atividades e tarefas que são específicas para sua própria jornada de equipes.

>[!NOTE]
>Estas diretrizes se concentra somente nos planos de chamada, conferência de áudio e roteamento direto. Se estiver familiarizado com as equipes, analise a [Visão geral das equipes da Microsoft](teams-overview.md). Para obter orientações gerais para planejar a implantação de equipes, comece com [Deploy chat, equipes, canais e aplicativos em equipes da Microsoft](deploy-chat-teams-channels-microsoft-teams-landing-page.md).

Use as listas de verificação fornecidas para rastrear o status de cada atividade individual e a tarefa e ter a certeza de que você ainda não ignorados nenhuma etapa crítica. Cada atividade inclui uma descrição detalhada de ações necessárias e referências para obter informações adicionais que você pode usar para concluir essa atividade.

Embora seja recomendável que você siga as listas de verificação em ordem, a sequência exata dependerá do escopo de sua implantação e a configuração e a complexidade do seu ambiente. Eles estão organizados para dar suporte a qualquer um "em ambiente intacto" às equipes de implantação (com nenhum Skype anterior para presença Online de negócios um) ou a migração do Skype para Business Online para equipes. Se você estiver migrando do Skype para Business Online, você talvez já tenha concluído algumas dessas atividades e ignorá-las agora.

Quando você estiver inclusão de usuários em uma base por site, é altamente recomendável que você use o [Site Playbook de habilitação para voz (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) como um guia suplementar estas listas de verificação.

>[!NOTE]
>A maioria das definições de configuração são comuns entre equipes e Skype para negócios Online. Você pode usar o Centro de administração do Centro de administração do Office 365 e Teams da Microsoft para definir essas configurações.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Pontos de decisão</td><td><ul><li>Quem será responsável pela supervisão a conclusão das listas de inclusão de verificação?</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Próximas etapas</td><td><ul><li>Baixe as listas de verificação de inclusão.</li><li>Trabalhar através dos itens de lista de verificação de inclusão passo a passo de acordo com o plano de implantação da sua organização.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="continue-onboarding"></a>Continuar a inclusão

Após concluir estas listas de verificação, você vai adicionou com êxito os recursos de voz à sua implantação de equipes.

Como a próxima etapa, use a [Guia estratégico de habilitação de Site para voz (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) para ajudá-lo a seus usuários em cada site integrado e ajudar a garantir que você planejar e executar atividades importantes de específicas do site.

-   Plano de implementação de sites por pronto

-   Estabelecer o processo de gerenciamento de serviço

-   Executar o teste e remediação

<!--ENDOFSECTION-->

## <a name="test-cloud-voice-workloads-in-teams"></a>Cargas de trabalho de voz nuvem de teste em equipes

Após você ter definido e documentado seu sucesso nos negócios equipes nuvem voz e planos de implementação técnica como parte da fase Envision e feita a configuração desejada no Centro de administração, a próxima etapa é validar que sua organização as expectativas e requisitos são atendidos por meio do recurso, a funcionalidade e usabilidade. Você deve realizar esta etapa de validação antes de implantar uma implantação piloto ou final em seu ambiente de produção.

Você pode aproveitar o plano de sucesso de negócios que você definiu durante a fase de Envision para servir como base para determinar as atividades, as expectativas, casos de teste de funcionalidade do recurso e escopo geral a ser avaliada durante a fase de teste.

## <a name="define-your-testing-approach"></a>Definir sua abordagem de teste

Na sua forma mais simples, sua abordagem do teste se baseia em sua revisar os recursos de conferências de áudio, chamar planos, ou plano de serviço de roteamento direto e desenvolvendo um teste verificar se os seus requisitos de funcionalidade foram atendidos para usuários no escopo. A seguir está um plano de teste de exemplo para a fase de Onboard de uma implementação de serviços de audioconferência.


| Recurso de conferência de áudio para testar | Resumo dos resultados | Observações adicionais |
|------------|-----------------|------------------|
| Agendar uma reunião de equipes do ad-hoc que contém informações de discagem de conferência de áudio | Aprovação/reprovação   | TBD |
| Usar um telefone para áudio da reunião discando em uma reunião da PSTN com as informações de discagem fornecidas | Aprovação/reprovação | TBD |
| Ingressar em outras pessoas a uma reunião existente discando a eles através da PSTN | Aprovação/reprovação | TBD |



| Roteamento direto ou em chamada planos de recurso para testar | Resumo dos resultados | Observações adicionais |
|----------------------------------------------------|-----------------|------------------|
| Fazer uma chamada PSTN, discando um número PSTN       | Aprovação/reprovação       | TBD |
| Receber uma chamada PSTN discando o número do seu PSTN a partir de uma linha externa (linha fixa a móvel) | Aprovação/reprovação | TBD|
| Transferir uma chamada PSTN de um usuário de equipes para outro | Aprovação/reprovação | TBD |


>[!TIP]
>Para auxiliar na criação de caso de teste como um ponto de partida, consulte a lista de usuário orientação disponível em [equipes reuniões e chamadas](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings).

<!--ENDOFSECTION-->

## <a name="set-up-cloud-voice-workloads-for-teams"></a>Configurar as cargas de trabalho de voz de nuvem para equipes

Agora que você definiu sua abordagem de teste, a próxima etapa é configurar o seu ambiente de serviço e os usuários no escopo para recursos de voz de nuvem de equipes.

Para obter informações adicionais, consulte:

- [Planejamento técnico da Audioconferência](audio-conferencing.md#technical-planning-for-audio-conferencing)

- [Configurar Audioconferência no Microsoft Teams](set-up-audio-conferencing-in-teams.md)

- [Técnicas de planejamento para o sistema telefônico com a chamada de planos](calling-plan-landing-page.md)

- [Configure planos de chamar para Skype para negócios e Teams da Microsoft](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

- [Planejar o Roteamento Direto](https://docs.microsoft.com/microsoftteams/direct-routing-plan)

- [Configurar o Roteamento Direto](https://docs.microsoft.com/microsoftteams/direct-routing-configure)

### <a name="execute-the-test-plan"></a>Executar o plano de teste

[//]: # (Editar okey? "Usuário" parecia um pouco ambíguo para mim.)
Depois que o ambiente do usuário e o serviço tiverem sido configurados, a última etapa de teste inclui a execução de plano de teste com foco na validação de funcionalidade e recursos. 

**Serviços de audioconferência testes pré-requisitos e suposições para sites e usuários no escopo:**

-   Negócios usar definição de maiusculas para a conferência de áudio serviço foi concluído.

-   Licenciamento necessários para conferência de áudio está disponível e foi atribuído.

-   A lista de sites organizacionais e de grupos de usuários foram identificados.

-   A lista de serviços de audioconferência dedicado e compartilhado discar números com preferência de idioma foram identificados e configurados.

-   [Créditos de comunicações](what-are-communications-credits.md) (se necessário) tiverem sido configurados para sua organização.

-   Configurações de ponte de conferência de áudio conferência foram identificados e configurado (tamanho do PIN, notificações de entrada/saída, preferência de notificação de habilitação).

-   Políticas de conferência de locatários e configurações que oferecem suporte a conferência de áudio cenários de discagem foram identificados, configurados e aplicados do plano de discagem.

-   Requisitos de conformidade de conferência de áudio foram identificados e configurados.

**Planos de testes de pré-requisitos e suposições para sites e usuários no escopo de chamada:**

-   Negócios usar definição de maiusculas para a chamada planos de serviço foi concluído.

-   Necessário para chamar planos de licenciamento está disponível e foi atribuído.

-   A lista de sites organizacionais e de grupos de usuários foram identificados.

-   Números de telefone a ser atribuído aos usuários foram adquiridos ou migrados para o Microsoft e estão disponíveis no portal do inquilino.

-   [Créditos de comunicações](what-are-communications-credits.md) (se necessário) tiverem sido configurados para sua organização.

-   Diretivas de usuário de Inquilino e configurações de plano de discagem que fundamentam os cenários de planos de chamar foram identificadas, configuradas e aplicadas.

-   Chamando planos de requisitos de conformidade foram identificados e configurados.

**Testes de pré-requisitos e suposições para sites e usuários no escopo de roteamento direto:**

-   Negócios usar definição de maiusculas para o roteamento direto serviço foi concluído.

-   Licenciamento necessários para roteamento direto está disponível e foi atribuído.

-   A lista de sites organizacionais e de grupos de usuários foram identificados.

-   Um [certificado do controlador de borda de sessão (SBC)](https://docs.microsoft.com/microsoftteams/direct-routing-plan#supported-session-border-controllers-sbcs) tenha sido implantado, configurado e juntamente com o sistema telefônico.

-   Voz empresarial tiver sido habilitada e os números de telefone que tiverem sido atribuídos.

-   Políticas de roteamento de voz foram identificadas, configuradas e atribuídas.

-   Microsoft Teams tiver sido definida como o cliente de chamada preferencial para os usuários no escopo.
 
-   Requisitos de conformidade de roteamento diretos foram identificados e configurados.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Pontos de decisão</td><td><ul><li>Decida quais recursos do recurso de conferência de áudio serão implantados (decisão de serviço).</li><li>Identifique os requisitos de funcionalidade do usuário para conferência de áudio.</li><li>Identifique os requisitos de configuração do serviço de conferência de áudio.</li><br><li>Decida se roteamento direto ou chamar planos serão implantados e configurados.<li>Decida quais recursos do sistema telefônico serão implantados (decisão de serviço).</li><li>Identifique os requisitos de funcionalidade do usuário para planos de chamar ou roteamento direto.</li><li>Identifique o requisito de configuração de serviço para planos de chamar ou roteamento direto.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Próximas etapas</td><td><ul><li>Desenvolver e documentar sua abordagem de plano de teste.</li><li>Prepare seu ambiente de serviço e os usuários no escopo de recursos de conferência de áudio.</li><li>Prepare seu ambiente de serviço e os usuários no escopo para recursos de roteamento direto ou em planos de chamada.</li><li>Execute o teste de validação para os recursos de conferência de áudio que você deseja habilitar.</li><li>Execute o teste de validação para os recursos de roteamento direto ou em planos de chamada que você deseja habilitar.</li><li>Para qualquer falhas de teste, confirme se sua configuração está correta, analise os artigos de comunidade, e — se for necessário — elevar um caso de suporte.</li></ul></td></tr>
</table>


Para obter orientações detalhadas adicionais sobre como executar o teste para conferência de áudio em equipes, consulte o [detalhadas testando guia para conferência de áudio](onboarding-test-plan-for-enterprises-Audio-Conferencing.md).

Para obter orientações detalhadas adicionais sobre como executar o teste chamar planos em equipes, consulte o [detalhadas testando guia para o sistema telefônico](onboarding-test-plan-for-enterprises-Phone-System.md).

<!--ENDOFSECTION-->
