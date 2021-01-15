---
title: Lista de verificação de atualização| Atualização do Skype Business para o Teams | Etapas básicas
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Siga este plano de ação acelerada de dez etapas para fazer a transição de uma configuração básica do Skype for Business para a configuração do Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- seo-marvel-apr2020
- Teams-upgrade-guidance
- ms.teamsadmincenter.dashboard.widget.upgrade.opt-in
- ms.teamsadmincenter.dashboard.widget.upgrade.opt-out
- ms.teamsadmincenter.dashboard.widget.upgrade.scheduled
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 37cc9f3940eb08a4df092042c016b194b01c64e6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809081"
---
# <a name="upgrade-basic"></a>Upgrade Basic

<a name="about-upgrade-basic"></a>

Projetado apenas para organizações menores ou aquelas que usam o Skype for Business Online para IM (chat) e reuniões, a lista de verificação Upgrade Basic é um plano de ação acelerada que inclui atividades básicas, recomendadas e recursos associados para implementar uma mudança bem-sucedida do Skype for Business para o Teams.

Essas dez etapas fáceis fornecem tudo o que você precisa para uma atualização bem-sucedida. Elas foram projetadas para serem concluídas em cerca de 30 a 45 dias, mas você deve ajustar as datas de conclusão das tarefas com base no cronograma de atualização da sua organização.

> [!IMPORTANT]
> O Skype for Business Online será retirado em 31 de julho de 2021. Após esse período, o serviço do Skype for Business Online não estará mais acessível ou terá suporte. Para maximizar a realização dos benefícios e garantir que sua organização tenha tempo adequado para implementar a atualização, recomendamos que você comece hoje sua jornada para o Microsoft Teams.

O que acontece com o Skype for Business após a atualização? Depois que seus usuários forem atualizados para o Teams (modo **Apenas Teams**):

- O cliente Skype for Business está desabilitado, e todas as chamadas e chats vão para o Teams. Observe que isso não desinstalará o cliente em suas áreas de trabalho.
- Todas as reuniões do Skype for Business agendadas antes da atualização funcionam conforme projetado, mas todas as novas reuniões são agendadas no Teams. O plug-in do Skype for Business não estará mais disponível no Outlook. 
- Se os usuários tentarem entrar no Skype for Business, eles receberão uma notificação do cliente de que foram atualizados para o Teams.
- Os usuários precisam desinstalar manualmente o cliente Skype for Business em seus dispositivos móveis.

Consulte nossas [perguntas frequentes](https://aka.ms/SkypeToTeams-FAQ) sobre a atualização.

Não está familiarizado com o Teams? [Leia](https://products.office.com/microsoft-teams/group-chat-software) sobre como o Teams reúne conversas, reuniões, arquivos, aplicativos do Office e integrações de terceiros, fornecendo um único hub para o trabalho em equipe no Microsoft 365 e no Office 365.

<!--ENDOFSECTION-->

<a name="step-1"></a>

## <a name="step-1-notify-your-key-stakeholders"></a>Etapa 1. Notificar seus principais participantes

*(Cerca de quatro a seis semanas antes da atualização)*

Os líderes sênior são responsáveis pelo sucesso da empresa; certifique-se de mantê-los no saber sobre as alterações de tecnologia. Como é possível que nem todas as pessoas receberam ou lerem a notificação de qualificação de atualização, você precisa informar seus stakeholders (por exemplo, CEO, profissionais de TI, Marketing e líder de helpdesk) antes de começar a planejar a atualização.

**Recursos:**

- [Exemplo de email: comunicação do stakeholder](upgrade-emails-surveys.md#step-1-email)

[Retornar ao topo](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-2"></a>

## <a name="step-2-prepare-your-organization-for-teams"></a>Etapa 2. Preparar sua organização para o Teams

*(Cerca de quatro a seis semanas antes da atualização)*

O Teams oferece funcionalidade compatível com o Skype for Business, como IM (chat) e reuniões, mas também pode fazer muito mais. Como um verdadeiro hub para o trabalho em equipe, o Teams permite que grupos de trabalho gerenciem projetos, arquivos, conversas e aplicativos em um único local. Por padrão, o Microsoft Teams é ativado para todas as organizações. Decida como sua organização usará o Teams e configurará seu ambiente para sucesso. 

> [!Note]
> Como um cliente existente do Skype for Business, sua infraestrutura de rede atual provavelmente já está configurada para o Teams. Para confirmar isso, você pode seguir as diretrizes de "Planejamento técnico completo" vinculadas a seguir (isso é opcional).

**Recursos:**

- [Visão geral do Teams](Teams-overview.md)
- [Introdução ao Microsoft Teams](get-started-with-teams-quick-start.md)

[Retornar ao topo](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-3"></a>

## <a name="step-3-know-your-skype-for-business-users"></a>Etapa 3. Conheça seus usuários do Skype for Business

*(Cerca de quatro semanas antes da atualização)*

Os usuários profundamente adotados no Skype for Business podem precisar de um pouco mais de tempo ou assistência para fazer a transição para o Teams. Aproveite para revisar o uso atual do Skype for Business para identificar os principais usuários que precisam de suporte adicional e estabelecer uma linha de base de uso que você pode acompanhar em relação aos seus números pós-atualização.

**Recursos:**

- [Relatórios do Microsoft 365 no centro de administração](https://docs.microsoft.com/microsoft-365/admin/activity-reports/activity-reports)

[Retornar ao topo](#about-upgrade-basic)

<a name="step-4"></a>

<!--ENDOFSECTION-->

## <a name="step-4-notify-your-users-that-theyll-be-upgrading-from-skype-for-business-to-teams"></a>Etapa 4. Notificar os usuários de que eles atualizarão do Skype for Business para o Teams

*(Cerca de duas a três semanas antes da atualização)*

Fornecer um aviso amplo aos seus usuários dará tempo para que eles se familiarizarem com o Teams sem afetar negativamente sua produtividade, resultando em uma experiência de usuário mais positiva. Envie uma comunicação para dizer a eles o que está mudando, por que está mudando e como eles podem se preparar para isso.

> [!Note]
> Se necessário, você pode habilitar o Teams para seus usuários por meio do Centro de administração do Microsoft 365 neste momento.

**Recursos:**

- [Gerenciar as configurações do Microsoft Teams para sua organização](enable-features-office-365.md)
- [Exemplo de email: comunicado aos usuários sobre o Skype for Business](upgrade-emails-surveys.md#step-4-email)

[Retornar ao topo](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-5"></a>

## <a name="step-5-activate-the-user-upgrade-notification"></a>Etapa 5. Ativar a notificação de atualização do usuário

*(Cerca de uma semana antes da atualização)*

Mantenha a dinâmica de atualização habilitando a notificação de atualização do usuário por meio do portal de administração, fornecendo um alerta visual no cliente Skype for Business de que os usuários estão sendo atualizados do Skype for Business para o Teams.

**Recursos:**

- [Definir suas configurações de coexistência e atualização](setting-your-coexistence-and-upgrade-settings.md)

[Retornar ao topo](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-6"></a>

## <a name="step-6-remind-your-users-that-theyll-be-upgrading-from-skype-for-business-to-teams"></a>Etapa 6. Lembre os usuários de que eles atualizarão do Skype for Business para o Teams

*(Cerca de cinco dias antes da atualização)*

Os usuários estão ocupados com suas responsabilidades diárias. Lembrar-lhes da atualização pendente ajudará a garantir que eles se lembre de seguir as etapas necessárias para se preparar para o Teams. Esse é o momento perfeito para lembrar os usuários sobre o treinamento disponível e como começar a usar o Teams.

**Recursos:**

- [Exemplo de email: lembrar os usuários de começar a trabalhar com o Teams](upgrade-emails-surveys.md#step-6-email)

[Retornar ao topo](#about-upgrade-basic)

<a name="step-7"></a>

<!--ENDOFSECTION-->

## <a name="step-7-upgrade-users-to-teams"></a>Etapa 7. Atualize os usuários para o Teams!

*(Dia da Atualização)*

Hoje é o dia em que sua organização atualiza oficialmente para o Teams como sua solução de comunicação e colaboração. No centro de administração do Microsoft Teams, ative a opção de atualização definindo o modo de coexistência como **Somente Teams.** (No centro de administração, vá para **Configurações de toda a organização**  >  **Atualização do Teams**.) Os usuários receberão uma notificação no cliente Skype for Business de que foram atualizados para o Teams.

Recomendamos que, depois que todos foram atualizados, você envie um email enviando-os para o Teams.

**Recursos:**

- [Definir suas configurações de coexistência e atualização](setting-your-coexistence-and-upgrade-settings.md)
- [Exemplo de email: bem-vindo aos usuários do Teams](upgrade-emails-surveys.md#step-7-email)

[Retornar ao topo](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-8"></a>

## <a name="step-8-monitor-teams-usage-against-your-baseline"></a>Etapa 8. Monitorar o uso do Teams em relação à linha de base

*(Cerca de uma ou duas semanas após a atualização)*

O ajuste a uma nova tecnologia pode levar algum tempo. Verifique o uso para verificar se os usuários estão usando o Teams no mesmo nível — ou superior — como fizeram com o Skype for Business. Entre com usuários que não estão usando o Teams nos níveis esperados.

**Recursos:**

- [Ver dados de uso](https://portal.office.com/AdminPortal/Home#/reportsUsage)

[Retornar ao topo](#about-upgrade-basic)

<a name="step-9"></a>

<!--ENDOFSECTION-->

## <a name="step-9-measure-user-satisfaction"></a>Etapa 9. Medir a satisfação do usuário

*(Cerca de uma ou duas semanas após a atualização)*

A satisfação do funcionário pode influenciar a produtividade, a retenção e, por fim, os resultados de negócios. Entre em contato com seus usuários para avaliar o sentimento do usuário sobre a atualização e sua satisfação com o Teams.

**Recursos:**

- [Exemplo de email: fazer check-in com usuários](upgrade-emails-surveys.md#step-9-email), além [de pesquisas de usuário](upgrade-emails-surveys.md#step-9-surveys)

[Retornar ao topo](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-10"></a>

## <a name="step-10-maximize-your-roi-with-teams"></a>Etapa 10. Maximizar seu ROI com o Teams

*(Contínuo)*

Depois que os usuários se familiarizarem com mensagens de IM (chat) e reuniões no Teams, incentive-os a estender seu caso de uso usando a colaboração do Teams e a integração de aplicativos, otimizando realmente a nova solução e maximizando um retorno sobre seu investimento.

**Recursos:**

- [Exemplo de email: incentivar os usuários a explorar ainda mais o Teams](upgrade-emails-surveys.md#step-10-email)

[Retornar ao topo](#about-upgrade-basic)
