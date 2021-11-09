---
title: Lista de verificação de atualização| Skype Business to Teams Upgrade | Etapas básicas
author: HowlinWolf-92
ms.author: v-mahoffman
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Siga este plano de ação de dez etapas acelerado para fazer a transição de uma configuração Skype for Business base para a Microsoft Teams configuração.
ms.localizationpriority: medium
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
ms.openlocfilehash: 7c0017169ce8cb96b9c8ea1ba871eb9e21101025
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60851635"
---
# <a name="upgrade-basic"></a>Upgrade Basic

<a name="about-upgrade-basic"></a>

Projetada para organizações menores ou que usam o Skype for Business Online apenas para IM (chat) e reuniões, a lista de verificação Upgrade Basic é um plano de ação acelerado que inclui atividades básicas, recomendadas e recursos associados para implementar uma movimentação bem-sucedida do Skype for Business para o Teams.

Essas dez etapas fáceis fornecem tudo o que você precisa para uma atualização bem-sucedida. Eles foram projetados para serem concluídos em cerca de 30 a 45 dias, mas você deve ajustar as datas de conclusão da tarefa com base no cronograma de atualização da sua organização.

> [!IMPORTANT]
> Skype for Business Online será retirado em 31 de julho de 2021. Após esse tempo, o Skype for Business online não estará mais acessível ou com suporte. Para maximizar a realização dos benefícios e garantir que sua organização tenha tempo adequado para implementar a atualização, recomendamos que você comece hoje sua jornada para o Microsoft Teams.

O que acontece com Skype for Business após a atualização? Depois que seus usuários forem atualizados para o Teams (modo **Apenas Teams**):

- O Skype for Business cliente está desabilitado, e todos os chats e chamadas vão para Teams. Observe que isso não desinstalará o cliente em suas áreas de trabalho.
- Todas Skype for Business reuniões agendadas antes da atualização funcionam como projetadas, mas todas as novas reuniões são agendadas em Teams. O Skype for Business plug-in do Outlook. 
- Se os usuários tentarem entrar Skype for Business, eles receberão uma notificação de seu cliente de que foram atualizados para Teams.
- Os usuários precisam desinstalar manualmente o Skype for Business cliente em seus dispositivos móveis.

Consulte nossas [perguntas frequentes](./faq-journey.yml) sobre a atualização.

Não está familiarizado com Teams? [Leia sobre](https://products.office.com/microsoft-teams/group-chat-software) como o Teams reúne conversas, reuniões, arquivos, aplicativos Office e integrações de terceiros, fornecendo um único hub para o trabalho em equipe no Microsoft 365 e Office 365.

<!--ENDOFSECTION-->

<a name="step-1"></a>

## <a name="step-1-notify-your-key-stakeholders"></a>Etapa 1. Notificar seus principais participantes

*(Cerca de quatro a seis semanas antes da atualização)*

Os líderes sênior são responsáveis pelo sucesso da empresa; certifique-se de mantê-los no know about technology changes. Como é possível que nem todos receberam ou lerem a notificação de qualificação de atualização, você precisa informar seus participantes (por exemplo, CEO, profissionais de TI, Marketing e leads de ajuda) antes de começar a planejar a atualização.

**Recursos:**

- [Exemplo de email: comunicação de stakeholders](upgrade-emails-surveys.md#step-1-email)

[Retornar ao topo](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-2"></a>

## <a name="step-2-prepare-your-organization-for-teams"></a>Etapa 2. Preparar sua organização para o Teams

*(Cerca de quatro a seis semanas antes da atualização)*

Teams oferece funcionalidades Skype for Business compatíveis, como IM (chat) e reuniões, mas também pode fazer muito mais. Como um verdadeiro hub para trabalho em equipe, o Teams permite que grupos de trabalho gerenciem projetos, arquivos, conversas e aplicativos em um único local. Por padrão, o Microsoft Teams é ativado para todas as organizações. Decida como sua organização usará o Teams e configure seu ambiente para o sucesso. 

> [!Note]
> Como um cliente Skype for Business existente, sua infraestrutura de rede atual provavelmente já está configurada para Teams. Para confirmar isso, você pode seguir as diretrizes de "Planejamento técnico completo" vinculadas a seguir (isso é opcional).

**Recursos:**

- [Visão geral do Teams](Teams-overview.md)
- [Introdução ao Microsoft Teams](get-started-with-teams-quick-start.md)

[Retornar ao topo](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-3"></a>

## <a name="step-3-know-your-skype-for-business-users"></a>Etapa 3. Conheça seus Skype for Business usuários

*(Cerca de quatro semanas antes da atualização)*

Os usuários que são profundamente adotados no Skype for Business podem precisar de um pouco mais de tempo ou assistência para fazer a transição para Teams. Leve tempo para analisar o uso atual Skype for Business para identificar seus principais usuários que precisam de suporte adicional e para estabelecer uma linha de base de uso que você pode acompanhar em relação aos seus números pós-atualização.

**Recursos:**

- [Microsoft 365 relatórios no centro de administração](/microsoft-365/admin/activity-reports/activity-reports)

[Retornar ao topo](#about-upgrade-basic)

<a name="step-4"></a>

<!--ENDOFSECTION-->

## <a name="step-4-notify-your-users-that-theyll-be-upgrading-from-skype-for-business-to-teams"></a>Etapa 4. Notifique seus usuários de que eles estarão atualizando de Skype for Business para Teams

*(Cerca de duas a três semanas antes da atualização)*

Fornecer um aviso amplo aos usuários dará tempo para que eles se familiarizarem com o Teams sem afetar negativamente sua produtividade, resultando em uma experiência de usuário mais positiva. Envie uma comunicação para dizer a eles o que está mudando, por que ela está mudando e como eles podem se preparar para isso.

> [!Note]
> Se necessário, você pode habilitar Teams para seus usuários por meio do Centro de administração do Microsoft 365 no momento.

**Recursos:**

- [Gerenciar as configurações do Microsoft Teams para sua organização](enable-features-office-365.md)
- [Exemplo de email: comunicado aos usuários sobre Skype for Business](upgrade-emails-surveys.md#step-4-email)

[Retornar ao topo](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-5"></a>

## <a name="step-5-activate-the-user-upgrade-notification"></a>Etapa 5. Ativar a notificação de atualização do usuário

*(Cerca de uma semana antes da atualização)*

Mantenha o momento de atualização habilitando a notificação de atualização do usuário por meio do portal de administração, fornecendo um alerta visual no cliente Skype for Business que os usuários estão sendo atualizados de Skype for Business para Teams.

**Recursos:**

- [Definir suas configurações de coexistência e atualização](setting-your-coexistence-and-upgrade-settings.md)

[Retornar ao topo](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-6"></a>

## <a name="step-6-remind-your-users-that-theyll-be-upgrading-from-skype-for-business-to-teams"></a>Etapa 6. Lembre os usuários de que eles estarão atualizando de Skype for Business para Teams

*(Cerca de cinco dias antes da atualização)*

Os usuários estão ocupados com suas responsabilidades diárias. Lembrá-los da atualização pendente ajudará a garantir que eles se lembre de tomar as etapas necessárias para se preparar para Teams. Este é o momento perfeito para lembrar os usuários sobre treinamento disponível e como começar a Teams.

**Recursos:**

- [Exemplo de email: lembre os usuários de começar a Teams](upgrade-emails-surveys.md#step-6-email)

[Retornar ao topo](#about-upgrade-basic)

<a name="step-7"></a>

<!--ENDOFSECTION-->

## <a name="step-7-upgrade-users-to-teams"></a>Etapa 7. Atualize os usuários para Teams!

*(Dia da Atualização)*

Hoje é o dia em que sua organização atualiza oficialmente para Teams como sua solução de comunicação e colaboração. No centro Microsoft Teams de administração, ative a opção de atualização definindo o modo de coexistência como **Teams Somente**. (No centro de administração, acesse **Org-wide Configurações**  >  **Teams Upgrade**.) Os usuários receberão uma notificação no Skype for Business cliente que foram atualizados para Teams.

Recomendamos que, depois que todos foram atualizados, você envie um email acolhendo-os para Teams.

**Recursos:**

- [Definir suas configurações de coexistência e atualização](setting-your-coexistence-and-upgrade-settings.md)
- [Exemplo de email: bem-vindo aos usuários Teams](upgrade-emails-surveys.md#step-7-email)

[Retornar ao topo](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-8"></a>

## <a name="step-8-monitor-teams-usage-against-your-baseline"></a>Etapa 8. Monitorar Teams uso em sua linha de base

*(Cerca de uma ou duas semanas após a atualização)*

O ajuste a uma nova tecnologia pode levar algum tempo. Verifique o uso para verificar se os usuários estão usando Teams no mesmo nível — ou maior — como fizeram com Skype for Business. Entre com usuários que não estão usando Teams níveis esperados.

**Recursos:**

- [Consulte dados de uso](https://portal.office.com/AdminPortal/Home#/reportsUsage)

[Retornar ao topo](#about-upgrade-basic)

<a name="step-9"></a>

<!--ENDOFSECTION-->

## <a name="step-9-measure-user-satisfaction"></a>Etapa 9. Medir a satisfação do usuário

*(Cerca de uma ou duas semanas após a atualização)*

A satisfação dos funcionários pode influenciar a produtividade, a retenção e, em última análise, os resultados dos negócios. Entre em contato com seus usuários para avaliar o sentimento do usuário sobre a atualização e sua satisfação com Teams.

**Recursos:**

- [Exemplo de email: fazer check-in com usuários](upgrade-emails-surveys.md#step-9-email), além [de pesquisas de usuário](upgrade-emails-surveys.md#step-9-surveys)

[Retornar ao topo](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-10"></a>

## <a name="step-10-maximize-your-roi-with-teams"></a>Etapa 10. Maximizar seu ROI com Teams

*(Em andamento)*

Depois que os usuários se sentem confortáveis com mensagens de IM (chat) e reuniões no Teams, incentive-os a estender seu caso de uso usando a colaboração Teams integração de aplicativos, otimizando verdadeiramente sua nova solução e maximizando um retorno sobre seu investimento.

**Recursos:**

- [Exemplo de email: incentivar os usuários a explorar Teams mais](upgrade-emails-surveys.md#step-10-email)

[Retornar ao topo](#about-upgrade-basic)