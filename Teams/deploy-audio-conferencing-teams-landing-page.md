---
title: Audioconferência no Microsoft Teams
description: Use esses recursos de implantação para ajudá-lo a implantar a audioconferência como parte da carga de trabalho das reuniões no Microsoft Teams.
ms.topic: article
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 01/28/2019
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
localization_priority: Priority
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 52077b5ac7ab9da52c894267153d4a342b651f7f
ms.sourcegitcommit: 3a0b90af8eb3c10579b9eea7837c60a19a577881
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/28/2019
ms.locfileid: "29595358"
---
# <a name="audio-conferencing-in-microsoft-teams"></a>Audioconferência no Microsoft Teams

A opção de Audioconferência é a capacidade de ingressar em uma reunião do Teams de um telefone comum e ligar de uma reunião para um número de telefone. Verifique se analisou a [Implementação de reuniões](deploy-meetings-microsoft-teams-landing-page.md) como parte da implementação da Audioconferência na organização.

## <a name="audio-conferencing-deployment-decisions"></a>Decisões de implantação da Audioconferência

Este artigo ajuda você a decidir se deseja alterar as configurações padrão de Audioconferência, com base no perfil da organização e requisitos de negócios e, em seguida, orienta você em cada alteração. Dividimos as configurações em dois grupos, começando com o conjunto principal de [alterações que você provavelmente realizará](#core-deployment-decisions). O segundo grupo inclui [configurações adicionais](#additional-deployment-decisions) que poderão ser configuradas com base nas necessidades de sua organização.

Basta configurar uma Audioconferência para as pessoas que planejam agendar ou liderar reuniões. Os participantes da reunião não precisam de licenças atribuídas ou de configuração adicional. É muito útil ligar para reuniões quando os usuários estão viajando e não podem participar de uma reunião usando o aplicativo Teams ou Skype for Business no laptop ou em dispositivos móveis. 


## <a name="audio-conferencing-prerequisites"></a>Provedores de Audioconferência 

Antes de implantar a Audioconferência no Teams, considere o seguinte:

|Pergunte-se|Ação |
|------------|-------|
|A Audioconferência está disponível para meu país/região?|Para descobrir se a Audioconferência está disponível em seu país/região, confira [Disponibilidade de Audioconferência e Planos de Chamadas por país e região](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).|
|Meus usuários têm licenciamento adequado para Audioconferência do Teams?|As licenças da Audioconferência está disponível como parte da assinatura do Office 365 E5 ou como um serviço de complemento à assinatura do Office 365 E1 ou Office 365 E3. <ul><li>Para obter e atribuir licenças, confira [Experimentar ou comprar a Audioconferência no Office 365](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365) e [Atribuir ou remover licenças do Office 365 para empresas](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</li><li> Para saber mais, confira [Licenciamento de complementos do Skype for Business e do Teams](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json). </li><li>Para ver quais recursos de nuvem estão incluídos em cada plano do Office 365, confira os artigos [Opções de Licença com base nos planos](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/office-365-business-premium-plan?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json).</li></ul>|
|Preciso comprar Créditos de Comunicação para os usuários que recebem licenças de Audioconferência?|Para saber mais, leia [O que são Créditos de Comunicação?](what-are-communications-credits.md) e, em seguida, confira a seção [Créditos de Comunicações](#communications-credits) abaixo.|
|||


## <a name="core-deployment-decisions"></a>Decisões principais de implantação

Depois de atender aos [Pré-requisitos de Audioconferência](#audio-conferencing-prerequisites), conclua as seguintes tarefas para configurar a Audioconferência para seus usuários.


### <a name="teams-administrators"></a>Administradores do Teams

O Teams oferece um conjunto personalizado de funções de administrador que pode ser usado para gerenciar o Teams para sua organização. As funções fornecem vários recursos para administradores. 

| Pergunte-se | Ação |
|--------------|--------|
|A quem será atribuída a função de Administrador de Comunicação do Teams?|Para saber mais sobre as funções de administrador do Teams, confira [Usar funções de administrador do Microsoft Teams para gerenciar o Teams](using-admin-roles.md).|
|A quem será atribuída função de Engenheiro de Suporte de Comunicações do Teams?|Para atribuir funções de administrador, confira [Atribuir funções de administrador e não administrador aos usuários com o Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).|
|A quem será atribuída a função de Especialista de Suporte de Comunicações do Teams?||
|||

### <a name="conferencing-bridges-and-phone-numbers"></a>Pontes de conferência e números de telefone

As pontes de conferência permitem que as pessoas liguem para reuniões usando um telefone. Você pode usar as configurações padrão em uma ponte de conferência ou alterar o número de telefone (chamada gratuita e tarifada) e outras configurações, como o PIN ou os idiomas serão usados.

Confira [Audioconferência no Office 365](audio-conferencing-in-office-365.md) para saber mais.

|Pergunte-se|Ação |
|------------|-------|
|Preciso adicionar novos números de ponte de conferência?| Para adicionar novos números, confira [Obter números de telefone de serviço](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json).|
|Será necessário modificar as configurações da ponte?|Para alterar essas configurações de ponte, confira [Alterar as configurações de uma ponte de Audioconferência](change-the-settings-for-an-audio-conferencing-bridge.md).|
|Preciso transferir números para usar na audioconferência?|Para saber mais sobre a portabilidade de números de telefone, leia [Transferir números de telefone para o Office 365](transfer-phone-numbers-to-office-365.md).|
|||


### <a name="default-and-alternate-languages"></a>Idiomas padrão e alternativos

A Audioconferência do Teams permite definir os idiomas padrão e alternativos para uma ponte de audioconferência.

|Pergunte-se|Ação |
|------------|-------|
| Quais idiomas devo escolher para as saudações do atendedor automático? | Para escolher idiomas, confira [Definir idiomas do atendedor automático da Audioconferência](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json).|
|||

### <a name="conferencing-bridge-settings"></a>Configurações de ponte de conferência 

Após configurar sua ponte de conferência, incluindo os idiomas padrão e alternativos, verifique se as configurações padrão, como notificações de entrada/saída e o comprimento do PIN, são aquelas que deseja usar. Caso contrário, você pode alterá-las. 

|Pergunte-se|Ação |
|------------|-------|
| Os participantes ouvirão uma notificação quando um usuário ingressar ou sair de uma reunião? | Para alterar essas configurações, confira [Alterar as configurações de uma ponte de Audioconferência](change-the-settings-for-an-audio-conferencing-bridge.md).|
|Qual é o comprimento necessário do PIN que um organizador de reuniões usa para iniciar a reunião?||
|||

### <a name="dial-in-phone-number-settings-for-users-who-lead-meetings"></a>Configurações de número de telefone de discagem para usuários que conduzem reuniões

Depois de criar sua ponte de Audioconferência, você precisa definir os números gratuitos e/ou tarifados que os usuários que conduzem as reuniões usarão.

|Pergunte-se|Ação |
|------------|-------|
| Quais números de ponte de conferência atribuirei a cada usuário que conduz reuniões? | Para atribuir um número de telefone de discagem a um usuário, confira [Etapa 7: atribuir números de telefone de discagem para usuários que conduzem reuniões](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing#step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json). |
|||

### <a name="communications-credits"></a>Créditos de Comunicação

Para fornecer números de telefone gratuitos de ponte de conferência e para oferecer suporte à discagem de conferência para números de telefone internacionais, você precisa configurar Créditos de Comunicação para sua organização. Para saber mais sobre os Créditos de Comunicação, confira [O que são Créditos de Comunicação?](what-are-communications-credits.md).

|Pergunte-se|Ação |
|------------|-------|
|Decida se os Créditos de Comunicação são necessários para a implementação da Audioconferência? |Para saber se é preciso configurar os Créditos de Comunicação, confira [Configurar Créditos de Comunicação para sua organização](set-up-communications-credits-for-your-organization.md).|
|Se eles forem necessários, quantos devo comprar?|Para determinar a quantidade de Créditos de Comunicações, confira [Valores de fundos recomendados](what-are-communications-credits.md#recommended-funding-amounts).|
|Devo configurar um valor para recarga automática?|Para configurar um valor de recarga automática, confira [Configurar Créditos de Comunicação para sua organização](what-are-communications-credits.md#recommended-funding-amounts).|
|||



## <a name="additional-deployment-decisions"></a>Decisões adicionais de implantação

Convém alterar essas configurações, com base nas necessidades da organização e da configuração.

### <a name="outbound-calling-restriction-policies"></a>Políticas de restrição de chamadas de saída 

Como administrador, você pode usar os controles de chamadas de saída para restringir o tipo de audioconferência e as chamadas PSTN de usuários finais que podem ser feitas pelos usuários em sua organização.

|Pergunte-se|Ação |
|------------|-------|
| Desejo limitar o tipo de chamadas de saída que são permitidas? | Para restringir chamadas de saída, confira [Políticas de restrição de chamadas de saída para audioconferência e chamadas PSTN do usuário](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/outbound-calling-restriction-policies?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json).|
|||


### <a name="dial-plans"></a>Planos de discagem

Um plano de discagem, um Sistema de Telefonia no Office 365, é um conjunto de regras de normalização que converte números telefônicos discados em um formato alternativo (normalmente no formatoE.164) para autorização de chamada e roteamento de chamada.

Para obter mais informações sobre os planos de discagem, confira [O que são os planos de discagem?](what-are-dial-plans.md)

|Pergunte-se|Ação |
|------------|-------|
|Minha organização precisa de um plano de discagem personalizado?|Para determinar se você precisa de um plano de chamadas personalizados, confira [Planejar planos de discagem para locatários](what-are-dial-plans.md#planning-for-tenant-dial-plans). |
|Quais usuários exigem um plano de discagem personalizado e qual plano de discagem de locatários deve ser atribuído a cada usuário?|Para adicionar usuários a um plano de discagem personalizado usando o PowerShell, confira [Criar e gerenciar planos de discagem](create-and-manage-dial-plans.md).|
|||

### <a name="troubleshoot-meeting-and-call-quality"></a>Resolver problemas de qualidade de chamadas e reuniões 

O Teams oferece duas maneiras de monitorar e solucionar problemas de qualidade da chamada: [Análise de chamadas e Painel de qualidade da chamadas](difference-between-call-analytics-and-call-quality-dashboard.md). A Análise de chamadas exibe informações detalhadas sobre os dispositivos, redes e conectividade relacionados a chamadas e reuniões específicas para cada usuário. A Análise de chamadas foi desenvolvida para ajudar administradores e agentes do suporte técnico a solucionar problemas de qualidade de chamadas com chamadas específicas, enquanto o Painel de qualidade de chamadas foi desenvolvido para ajudar administradores e engenheiros de rede a otimizar uma rede. O Painel de qualidade da chamadas desloca o foco de usuários específicos e, em vez disso, analisa as informações agregadas de toda a organização do Teams. 

|Pergunte-se|Ação |
|------------|-------|
| Quem será responsável pelo monitoramento e a solução de problemas de qualidade da chamada? | Confira [Usar a Análise de chamadas para solucionar problemas de baixa qualidade de chamadas](use-call-analytics-to-troubleshoot-poor-call-quality.md) para obter informações sobre os níveis de permissão necessários para solucionar problemas de qualidade de chamadas.|
|||


## <a name="next-steps"></a>Próximas etapas
- [Direcionar a adoção](adopt-microsoft-teams-landing-page.md) da audioconferência em sua organização.
- [Implementar o Cloud Voice](cloud-voice-landing-page.md)
- Incluir os aplicativos em destaque, como o Planner, na implementação inicial do Teams. Adicionar outros [aplicativos, bots e conectores](deploy-apps-microsoft-teams-landing-page.md) ao direcionar a adoção do Teams.
