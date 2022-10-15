---
title: Definir configurações de videoconferência – Microsoft Teams
ms.reviewer: ''
description: Use esses recursos de implantação para ajudá-lo a implantar a audioconferência como parte da carga de trabalho das reuniões no Microsoft Teams.
ms.topic: article
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
audience: admin
ms.date: 01/28/2019
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
ms.custom:
- seo-marvel-mar2020
f1.keywords:
- NOCSH
ms.localizationpriority: high
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7fafebf61cdf7e5b13cfbb6aaf08d73afef6f436
ms.sourcegitcommit: 50ae550b738424b35df1636590831e6c124ca0c1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/14/2022
ms.locfileid: "68576437"
---
# <a name="learn-how-to-deploy-audio-conferencing-in-microsoft-teams"></a>Saiba como implantar audioconferência no Microsoft Teams

A opção de Audioconferência é a capacidade de ingressar em uma reunião do Teams de um telefone comum e ligar de uma reunião para um número de telefone. Verifique se analisou a [Implementação de reuniões](deploy-meetings-microsoft-teams-landing-page.md) como parte da implementação da Audioconferência na organização.

## <a name="audio-conferencing-deployment-decisions"></a>Decisões de implantação da Audioconferência

Este artigo ajuda você a decidir se deseja alterar as configurações padrão de Audioconferência, com base no perfil da organização e requisitos de negócios e, em seguida, orienta você em cada alteração. Dividimos as configurações em dois grupos, começando com o conjunto principal de [alterações que você provavelmente realizará](#core-deployment-decisions). O segundo grupo inclui [configurações adicionais](#additional-deployment-decisions) que poderão ser configuradas com base nas necessidades da organização.

Basta configurar uma Audioconferência para as pessoas que planejam agendar ou liderar reuniões. Os participantes da reunião não precisam de licenças atribuídas ou de configuração adicional. Discar (ligar) para reuniões é muito útil para usuários que estão em trânsito e não podem participar de uma reunião usando o aplicativo Teams em seus laptops ou dispositivos móveis.

## <a name="audio-conferencing-prerequisites"></a>Provedores de Audioconferência

Antes de implantar a Audioconferência no Teams, considere o seguinte:

|Pergunte-se|Ação |
|------------|-------|
|A Audioconferência está disponível para meu país/região?|Para descobrir se a Audioconferência está disponível em seu país/região, confira [Disponibilidade de Audioconferência e Planos de Chamadas por país e região](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).|
|Meus usuários têm licenciamento adequado para audioconferência do Teams?|As licenças de audioconferência estão disponíveis como parte da assinatura do Microsoft 365 ou do Office 365 E5 ou como um serviço complementar à assinatura do Microsoft 365 Business Standard, E1 ou E3. <ul><li>Para obter e atribuir licenças, consulte [Atribuir ou remover licenças para Microsoft 365 Apps para Pequenos e Médios negócios](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</li><li> Para saber mais, leia [Licenciamento do complemento do Microsoft Teams](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md). </li><li>Para ver quais recursos de nuvem estão incluídos em cada plano, confira os artigos [Opções de Licença com base nos planos](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</li></ul>|
|Preciso comprar Créditos de Comunicação para os usuários que recebem licenças de audioconferência?|Para saber mais, leia [O que são Créditos de Comunicação?](what-are-communications-credits.md) e, em seguida, confira a seção [Créditos de Comunicações](#communications-credits) abaixo.|
|||

## <a name="core-deployment-decisions"></a>Decisões principais de implantação

Depois de atender aos Pré-requisitos de Audioconferência, conclua as seguintes tarefas para configurar a Audioconferência para seus usuários.

### <a name="teams-administrators"></a>Administradores do Teams

Teams provides a set of custom administrator roles that can be used to manage Teams for your organization. The roles provide various capabilities to administrators.

| Pergunte-se | Ação |
|--------------|--------|
|A quem será atribuída a função de Administrador de Comunicações de Equipes?|Para saber mais sobre as funções de administrador do Teams, confira [Usar funções de administrador para gerenciar o Microsoft Teams](using-admin-roles.md).|
|A quem será atribuída função de Engenheiro de Suporte de Comunicações de Equipes?|Para atribuir funções de administrador, confira [Atribuir funções de administrador e não administrador aos usuários com o Active Directory](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).|
|A quem será atribuída a função de Especialista de Suporte de Comunicações do Teams?||
|||

### <a name="conferencing-bridges-and-phone-numbers"></a>Pontes de conferência e números de telefone

Conferencing bridges let people dial into meetings using a phone. You can use the default settings for a conferencing bridge or change the phone numbers (toll and toll-free) and other settings, such as the PIN or the languages that are used.

Confira [Audioconferências](audio-conferencing-in-office-365.md) para saber mais.

|Pergunte a si mesmo|Ação |
|------------|-------|
|Preciso adicionar novos números de ponte de conferência?| Para adicionar novos números, confira [Obter números de telefone de serviço](./getting-service-phone-numbers.md).|
|Será necessário modificar as configurações da ponte?|Para alterar essas configurações de ponte, confira [Alterar as configurações de uma ponte de Audioconferência](change-the-settings-for-an-audio-conferencing-bridge.md).|
|Preciso transferir números para usar na audioconferência?|Para saber mais sobre a portabilidade de números de telefone, leia [Transferir números de telefone para o Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).|
|||

### <a name="default-and-alternate-languages"></a>Idiomas padrão e alternativos

A Audioconferência do Teams permite definir os idiomas padrão e alternativos para uma ponte de audioconferência.

|Pergunte-se|Ação |
|------------|-------|
| Quais idiomas devo escolher para as saudações do atendedor automático? | Para escolher idiomas, consulte [Definir idiomas de atendedor automático para Audioconferência no Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).|
|||

### <a name="conferencing-bridge-settings"></a>Configurações de ponte de conferência

After setting up your conferencing bridge, including default and alternate languages, you should verify that the default settings such as entry/exit notifications and PIN length are the ones you want to use. If they're not, you can change them.

|Pergunte a si mesmo|Ação |
|------------|-------|
| Os participantes ouvirão uma notificação quando um usuário ingressar ou sair de uma reunião? | Para alterar essas configurações, confira [Alterar as configurações de uma ponte de Audioconferência](change-the-settings-for-an-audio-conferencing-bridge.md).|
|Qual é o comprimento necessário do PIN que um organizador de reuniões usa para iniciar a reunião?||
|||

### <a name="dial-in-phone-number-settings-for-users-who-lead-meetings"></a>Configurações de número de telefone de discagem para usuários que conduzem reuniões

Depois de criar sua ponte de Audioconferência, você precisa definir os números gratuitos e/ou tarifados que os usuários que conduzem as reuniões usarão.

|Pergunte-se|Ação |
|------------|-------|
| Quais números de ponte de conferência atribuirei a cada usuário que conduz reuniões? | Para atribuir um número de telefone de discagem a um usuário, confira [Etapa 7: atribuir números de telefone de discagem para usuários que conduzem reuniões](set-up-audio-conferencing-in-teams.md#step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings). |
|||

### <a name="communications-credits"></a>Créditos de Comunicação

Para fornecer números de telefone gratuitos de ponte de conferência e para oferecer suporte à discagem de conferência para números de telefone internacionais, você precisa configurar Créditos de Comunicação para sua organização. Para saber mais sobre os Créditos de Comunicação, confira [O que são Créditos de Comunicação?](what-are-communications-credits.md).

|Pergunte-se|Ação |
|------------|-------|
|Decida se os Créditos de Comunicação são necessários para a implementação da Audioconferência? |Para saber se é preciso configurar os Créditos de Comunicação, confira [Configurar Créditos de Comunicação para sua organização](set-up-communications-credits-for-your-organization.md).|
|Se eles forem necessários, quantos devo comprar?|Para determinar a quantidade de Créditos de Comunicações, confira [Valores de fundos recomendados](what-are-communications-credits.md#recommended-funding-amounts).|
|Devo configurar um valor para recarga automática?|Para configurar um valor de recarga automática, confira [Configurar Créditos de Comunicação para sua organização](set-up-communications-credits-for-your-organization.md).|
|||

## <a name="additional-deployment-decisions"></a>Decisões adicionais de implantação

Convém alterar essas configurações, com base nas necessidades da organização e da configuração.

### <a name="outbound-calling-restriction-policies"></a>Políticas de restrição de chamadas de saída

Como administrador, você pode usar os controles de chamadas de saída para restringir o tipo de audioconferência e as chamadas PSTN de usuários finais que podem ser feitas pelos usuários em sua organização.

|Pergunte-se|Ação |
|------------|-------|
| Desejo limitar o tipo de chamadas de saída que são permitidas? | Para restringir chamadas de saída, confira [Políticas de restrição de chamadas de saída para audioconferência e chamadas PSTN do usuário](outbound-calling-restriction-policies.md).|
|||

### <a name="dial-plans"></a>Planos de discagem

Um plano de discagem, um Sistema de Telefonia no Microsoft 365 ou Office 365, é um conjunto de regras de normalização que converte números telefônicos discados em um formato alternativo (normalmente no formato E. 164) para autorização e roteamento de chamada.

Para obter mais informações sobre os planos de discagem, confira [O que são os planos de discagem?](what-are-dial-plans.md)

|Pergunte-se|Ação |
|------------|-------|
|Minha organização precisa de um plano de discagem personalizado?|Para determinar se você precisa de um plano de chamadas personalizados, confira [Planejar planos de discagem para locatários](what-are-dial-plans.md#planning-for-tenant-dial-plans). |
|Quais usuários exigem um plano de discagem personalizado e qual plano de discagem de locatários deve ser atribuído a cada usuário?|Para adicionar usuários a um plano de discagem personalizado usando o PowerShell, confira [Criar e gerenciar planos de discagem](create-and-manage-dial-plans.md).|
|||

### <a name="troubleshoot-meeting-and-call-quality"></a>Resolver problemas de qualidade de chamadas e reuniões

O Teams oferece duas maneiras de monitorar e solucionar problemas de qualidade da chamada: [Análise de Chamadas e Painel de Qualidade de Chamadas](monitor-call-quality-qos.md). A Análise de Chamadas exibe informações detalhadas sobre dispositivos, redes e conectividade relacionados a chamadas e reuniões específicas para cada usuário. A Análise de Chamadas foi desenvolvida para ajudar administradores e agentes de assistência técnica a solucionar problemas de qualidade de chamadas com chamadas específicas, enquanto o Painel de Qualidade de Chamadas foi desenvolvido para ajudar administradores e engenheiros de rede a otimizar uma rede. O Painel de Qualidade de Chamadas desloca o foco de usuários específicos e analisa as informações agregadas de toda a organização do Teams.

|Pergunte a si mesmo|Ação |
|------------|-------|
| Quem será responsável pelo monitoramento e a solução de problemas com a qualidade de chamadas? | Confira [Usar a Análise de chamadas para solucionar problemas de baixa qualidade de chamadas](use-call-analytics-to-troubleshoot-poor-call-quality.md) para obter informações sobre os níveis de permissão necessários para solucionar problemas de qualidade de chamadas.|
|||

## <a name="next-steps"></a>Próximas etapas

- [Direcionar a adoção](adopt-microsoft-teams-landing-page.md) da audioconferência em sua organização.
- [Implementar o Cloud Voice](cloud-voice-landing-page.md)
- Incluir os aplicativos em destaque, como o Planner, na implementação inicial do Teams. Adicione outros [aplicativos do Teams à](deploy-apps-microsoft-teams-landing-page.md) medida que você impulsiona a adoção do Teams.
