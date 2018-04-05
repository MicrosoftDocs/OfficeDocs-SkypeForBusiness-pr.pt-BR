---
title: Preparar para implantar o serviço de voz de nuvem Teams da Microsoft
author: rmw2890
ms.author: MyAdvisor
manager: lehewe
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Use as listas de verificação de inclusão preparar o Office 365 para equipes e configurar recursos principais de equipes, rede e cargas de trabalho de voz na nuvem.
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: a1e4b6e690450b8ec81209a0244769444ee2d30d
ms.sourcegitcommit: ffca287cf70db2cab14cc1a6cb7cea68317bedd1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/05/2018
---
# <a name="prepare-my-service"></a>Preparar o meu serviço

Este artigo fornece uma visão geral dos requisitos de preparação dos serviços de voz para sua organização de nuvem. Ao preparar-se adequadamente, você pode ser que você esteja pronto para fornecer recursos de voz para sua organização de nuvem.

## <a name="onboarding-checklists-for-microsoft-teams-voice-workloads"></a>Listas de verificação de inclusão for Microsoft Teams cargas de trabalho de voz

As listas de verificação a seguintes percorrer as etapas para implementar o sistema telefônico e conferência de áudio com recursos de planos de chamada no Microsoft Teams.

*  [Preparar o Office 365 para equipes](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-enable-office-365)

*  [Configurar os principais recursos de equipes](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-configure-microsoft-teams-core-capabilities)

*  [Configurar a rede](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-configure-networking)

*  [Configurar as cargas de trabalho de voz de nuvem em equipes](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams)

As tarefas e atividades nestas listas de verificação são core "tarefas pendentes" itens que se aplicam a todas as implantações de recursos de voz com as equipes de nuvem. Você pode personalizar as listas de verificação para incluir as atividades e tarefas que são específicas para sua própria jornada de equipes.

>[!NOTE]
>Esta orientação enfoca exclusivamente o sistema telefônico com planos de chamada e conferência de áudio. Se estiver familiarizado com as equipes, analise a [Visão geral das equipes da Microsoft](https://docs.microsoft.com/MicrosoftTeams/teams-overview). Para obter orientações gerais para planejar a implantação de equipes, consulte o [Guia de planejamento de equipes da Microsoft](https://docs.microsoft.com/MicrosoftTeams/quick-start-enable-teams).

Use as listas de verificação fornecidas para rastrear o status de cada atividade individual e a tarefa e ter a certeza de que você ainda não ignorados nenhuma etapa crítica. Cada atividade inclui uma descrição detalhada de ações necessárias e referências para obter informações adicionais que você pode usar para concluir essa atividade.

Embora seja recomendável que você siga as listas de verificação em ordem, a sequência exata dependerá do escopo de sua implantação e a configuração e a complexidade do seu ambiente. Eles estão organizados para dar suporte a qualquer um "em ambiente intacto" às equipes de implantação (com nenhum Skype anterior para presença Online de negócios um) ou a migração do Skype para Business Online para equipes. Se você estiver migrando do Skype para Business Online, você talvez já tenha concluído algumas dessas atividades e ignorá-las agora.

Quando você estiver inclusão de usuários em uma base por site, é altamente recomendável que você use o [Site Playbook de habilitação para voz (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) como um guia suplementar estas listas de verificação.

>[!NOTE]
>A maioria das definições de configuração são comuns entre equipes e Skype para negócios Online. Você pode usar Skype do Office 365 para centro de administração de empresa para definir essas configurações.

<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Pontos de decisão</td><td><ul><li>Quem será responsável pela supervisão a conclusão das listas de inclusão de verificação?</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Próximos passos</td><td><ul><li>Baixe as listas de verificação de inclusão.</li><li>Trabalhar através dos itens de lista de verificação de inclusão passo a passo de acordo com o plano de implantação da sua organização.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="continue-onboarding"></a>Continuar a inclusão

Depois de concluir esta lista de verificação, você vai adicionou com êxito os recursos de voz à sua implantação de equipes.

Como a próxima etapa, use a [Guia estratégico de habilitação de Site para voz (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) para ajudá-lo a seus usuários em cada site integrado e ajudar a garantir que você planejar e executar atividades importantes de específicas do site.

-   Plano de implementação de sites por pronto

-   Estabelecer o processo de gerenciamento de serviço

-   Executar o teste e remediação

<!--ENDOFSECTION-->

## <a name="test-cloud-voice-workloads-in-teams"></a>Cargas de trabalho de voz nuvem de teste em equipes

Após você ter definido e documentado seu sucesso nos negócios equipes nuvem voz e planos de implementação técnica como parte da fase Envision e feita a configuração desejada no Centro de administração, a próxima etapa é validar que sua organização as expectativas e requisitos são atendidos por meio do recurso, a funcionalidade e usabilidade. Você deve realizar esta etapa de validação antes de implantar uma implantação piloto ou final em seu ambiente de produção.

Você pode aproveitar o plano de sucesso de negócios que você definiu durante a fase de Envision para servir como base para determinar as atividades, as expectativas, casos de teste de funcionalidade do recurso e escopo geral a ser avaliada durante a fase de teste.

## <a name="define-your-testing-approach"></a>Definir sua abordagem de teste

Na sua forma mais simples, sua abordagem de teste baseia-se em sua revisar os recursos do sistema telefônico ou conferência de áudio com o serviço de chamar planos e desenvolver um plano de teste para verificar se seus requisitos de funcionalidade foram atendidos para usuários no escopo. A seguir está um plano de teste de exemplo para a fase de Onboard de uma implementação de serviços de audioconferência.

| Recurso de conferência de áudio para testar | Resumo dos resultados | Observações adicionais |
|------------|-----------------|------------------|
| Agendar uma reunião de equipes do ad-hoc que contém informações de discagem de conferência de áudio | Aprovação/reprovação   | TBD |
| Usar um telefone para áudio da reunião discando em uma reunião da PSTN com as informações de discagem fornecidas | Aprovação/reprovação | TBD |
| Ingressar em outras pessoas a uma reunião existente discando a eles através da PSTN | Aprovação/reprovação | TBD |


| Sistema de telefone com o recurso de chamada planos para testar | Resumo dos resultados | Observações adicionais |
|----------------------------------------------------|-----------------|------------------|
| Fazer uma chamada PSTN para discando um número PSTN       | Aprovação/reprovação       | TBD |
| Receber uma chamada PSTN discando o número do seu PSTN a partir de uma linha externa (linha fixa a móvel) | Aprovação/reprovação | TBD|
|Transferir uma chamada PSTN de um usuário de equipes para outro | Aprovação/reprovação | TBD |


>[!TIP]
>Para auxiliar na criação de caso de teste como um ponto de partida, consulte a lista de diretrizes de usuário de serviços de audioconferência disponível em [equipes reuniões e chamadas](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8?ui=en-US&rs=en-US&ad=US#bkmk_havingmeetings).

<!--ENDOFSECTION-->

## <a name="set-up-cloud-voice-workloads-for-teams"></a>Configurar as cargas de trabalho de voz de nuvem para equipes

Agora que você definiu sua abordagem de teste, a próxima etapa é configurar o seu ambiente de serviço e os usuários no escopo para recursos de voz de nuvem de equipes. Para obter informações adicionais, consulte [Planejamento técnica de conferência de áudio](https://docs.microsoft.com/microsoftteams/audio-conferencing#technical-planning-for-audio-conferencing) e [Configurar a conferência de áudio para Skype para equipes da Microsoft e de negócios](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing) além de [Planejamento técnico para o sistema telefônico com planos de chamada](https://docs.microsoft.com/microsoftteams/phone-system-with-calling-plans#technical-planning-for-phone-system-with-calling-plans) e [Set up Planos de chamada do Skype para equipes da Microsoft e de negócios](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

<!--ENDOFSECTION-->

### <a name="execute-the-test-plan"></a>Executar o plano de teste

Depois que os ambientes de serviço de conferência de áudio e usuário tiverem sido configurados, a última etapa de teste inclui a execução de plano de teste com foco na validação de funcionalidade e recursos. 

**Serviços de audioconferência testes pré-requisitos e suposições para sites e usuários no escopo:**

-   Negócios usar definição de maiusculas para a conferência de áudio serviço foi concluído.

-   Licenciamento necessários para conferência de áudio está disponível e foi atribuído.

-   A lista de sites organizacionais e de grupos de usuários foram identificados.

-   A lista de serviços de audioconferência dedicado e compartilhado discar números com preferência de idioma foram identificados e configurados.

-   [Créditos de comunicações](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits) (se necessário) tiverem sido configurados para sua organização.

-   Configurações de ponte de conferência de áudio conferência foram identificados e configurado (tamanho do PIN, notificações de entrada/saída, preferência de notificação de habilitação).

-   Políticas de conferência de locatários e configurações que oferecem suporte a conferência de áudio cenários de discagem foram identificados, configurados e aplicados do plano de discagem.

-   Requisitos de conformidade de conferência de áudio foram identificados e configurados.

**Sistema telefônico com chamar planos de testes de pré-requisitos e suposições para sites e usuários no escopo:**

-   Definição de casos de uso comercial para o sistema telefônico com planos de chamar o serviço foi concluída.

-   Necessário para o sistema telefônico com chamar planos de licenciamento está disponível e foi atribuído.

-   A lista de sites organizacionais e de grupos de usuários foram identificados.

-   Números de telefone a ser atribuído aos usuários foram adquiridos ou migrados para o Microsoft e estão disponíveis no portal do inquilino.

-   [Créditos de comunicações](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits) (se necessário) tiverem sido configurados para sua organização.

-   Diretivas de usuário de Inquilino e configurações de plano de discagem que suportam o sistema telefônico com cenários de planos de chamada foram identificadas, configuradas e aplicadas.

-   O sistema telefônico com planos de chamar os requisitos de conformidade foram identificados e configurados.

<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Pontos de decisão</td><td><ul><li>Decida quais recursos do recurso de conferência de áudio serão implantados (decisão de serviço).</li><li>Identifique os requisitos de funcionalidade do usuário para conferência de áudio.</li><li>Identifique os requisitos de configuração do serviço de conferência de áudio.</li><li>Decida qual sistema telefônico com recursos chamar planos de recurso será implantado (decisão de serviço).</li><li>Identifique os requisitos de funcionalidade do usuário para o sistema telefônico com planos de chamada.</li><li>Identifique o requisito de configuração de serviço para o sistema telefônico com planos de chamada.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Próximos passos</td><td><ul><li>Desenvolver e documentar sua abordagem de plano de teste.</li><li>Prepare seu ambiente de serviço e os usuários no escopo de recursos de conferência de áudio.</li><li>Prepare seu ambiente de serviço e os usuários no escopo para o sistema telefônico com recursos de planos de chamada.</li><li>Execute o teste de validação para os recursos de conferência de áudio que você deseja habilitar.</li><li>Execute validação de teste para o sistema telefônico com planos de chamar os recursos que você deseja habilitar.</li><li>Para qualquer falhas de teste, confirme se sua configuração está correta, analise os artigos de comunidade, e — se for necessário — elevar um caso de suporte.</li></ul></td></tr>
</table>


Para obter orientações detalhadas adicionais sobre como executar o teste para conferência de áudio em equipes, consulte o [detalhado testing guia para audioconferências] (https://docs.microsoft.com/MicrosoftTeams/onboarding-test-plan-for-enterprises-Audio-Conferencing).

Para obter orientações detalhadas adicionais sobre como executar o teste para o sistema telefônico com chamar planos em equipes, consulte o [detalhadas testando guia para o sistema telefônico](https://docs.microsoft.com/MicrosoftTeams/onboarding-test-plan-for-enterprises-Phone-System).

<!--ENDOFSECTION-->