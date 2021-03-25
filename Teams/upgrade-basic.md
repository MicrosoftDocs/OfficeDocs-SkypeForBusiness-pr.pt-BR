---
title: Lista de verificação de atualização| Atualização do Skype Business para o Teams | Etapas básicas
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Siga este plano de ação de dez etapas acelerado para fazer a transição de uma configuração básica do Skype for Business para a configuração do Microsoft Teams.
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
ms.openlocfilehash: d9453ad770b7ca21b5300b193cbafb932ea7645a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120522"
---
# <a name="upgrade-basic"></a>Upgrade Basic

<a name="about-upgrade-basic"></a>

Projetado para organizações menores ou aquelas que usam o Skype for Business Online apenas para IM (chat) e reuniões, a lista de verificação Upgrade Basic é um plano de ação acelerado que inclui atividades básicas, recomendadas e recursos associados para implementar uma movimentação bem-sucedida do Skype for Business para o Teams.

Essas dez etapas fáceis fornecem tudo o que você precisa para uma atualização bem-sucedida. Eles foram projetados para serem concluídos em cerca de 30 a 45 dias, mas você deve ajustar as datas de conclusão da tarefa com base no cronograma de atualização da sua organização.

> [!IMPORTANT]
> O Skype for Business Online será reformado em 31 de julho de 2021. Após esse tempo, o serviço skype for Business Online não será mais acessível ou suportado. Para maximizar a realização dos benefícios e garantir que sua organização tenha tempo adequado para implementar a atualização, recomendamos que você comece hoje sua jornada para o Microsoft Teams.

O que acontece com o Skype for Business após a atualização? Depois que seus usuários forem atualizados para o Teams (modo **Apenas Teams**):

- Seu cliente skype for Business está desabilitado, e todos os chats e chamadas vão para o Teams. Observe que isso não desinstalará o cliente em suas áreas de trabalho.
- Todas as reuniões do Skype for Business agendadas antes da atualização funcionam como projetadas, mas todas as novas reuniões são agendadas no Teams. O plug-in do Skype for Business não estará mais disponível no Outlook. 
- Se os usuários tentarem entrar no Skype for Business, eles receberão uma notificação de seu cliente de que foram atualizados para o Teams.
- Os usuários precisam desinstalar manualmente o cliente skype for Business em seus dispositivos móveis.

Consulte nossas [perguntas frequentes](./faq-journey.yml) sobre a atualização.

Não está familiarizado com o Teams? [Leia sobre como o Teams](https://products.office.com/microsoft-teams/group-chat-software) reúne conversas, reuniões, arquivos, aplicativos do Office e integrações de terceiros, fornecendo um único hub para o trabalho em equipe no Microsoft 365 e no Office 365.

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

O Teams oferece funcionalidade compatível com o Skype for Business, como IM (chat) e reuniões, mas também pode fazer muito mais. Como um verdadeiro hub para trabalho em equipe, o Teams permite que grupos de trabalho gerenciem projetos, arquivos, conversas e aplicativos em um único local. Por padrão, o Microsoft Teams é ativado para todas as organizações. Decida como sua organização usará o Teams e configurará seu ambiente para o sucesso. 

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

Os usuários profundamente adotados no Skype for Business podem precisar de um pouco mais de tempo ou assistência para fazer a transição para o Teams. Leve tempo para revisar seu uso atual do Skype for Business para identificar seus principais usuários que precisam de suporte adicional e para estabelecer uma linha de base de uso que você pode acompanhar em relação aos seus números pós-atualização.

**Recursos:**

- [Relatórios do Microsoft 365 no centro de administração](/microsoft-365/admin/activity-reports/activity-reports)

[Retornar ao topo](#about-upgrade-basic)

<a name="step-4"></a>

<!--ENDOFSECTION-->

## <a name="step-4-notify-your-users-that-theyll-be-upgrading-from-skype-for-business-to-teams"></a>Etapa 4. Notifique seus usuários de que eles estarão atualizando do Skype for Business para o Teams

*(Cerca de duas a três semanas antes da atualização)*

Fornecer um aviso amplo aos usuários dará tempo para que eles se familiarizarem com o Teams sem afetar negativamente sua produtividade, resultando em uma experiência de usuário mais positiva. Envie uma comunicação para dizer a eles o que está mudando, por que ela está mudando e como eles podem se preparar para isso.

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

Mantenha o momento de atualização habilitando a notificação de atualização do usuário por meio do portal de administração, fornecendo um alerta visual no cliente skype for Business de que os usuários estão sendo atualizados do Skype for Business para o Teams.

**Recursos:**

- [Definir suas configurações de coexistência e atualização](setting-your-coexistence-and-upgrade-settings.md)

[Retornar ao topo](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-6"></a>

## <a name="step-6-remind-your-users-that-theyll-be-upgrading-from-skype-for-business-to-teams"></a>Etapa 6. Lembre seus usuários de que eles estarão atualizando do Skype for Business para o Teams

*(Cerca de cinco dias antes da atualização)*

Os usuários estão ocupados com suas responsabilidades diárias. Lembrá-los da atualização pendente ajudará a garantir que eles se lembre de tomar as etapas necessárias para se preparar para o Teams. Este é o momento perfeito para lembrar os usuários sobre treinamento disponível e como começar com o Teams.

**Recursos:**

- [Exemplo de email: lembrar os usuários para começar com o Teams](upgrade-emails-surveys.md#step-6-email)

[Retornar ao topo](#about-upgrade-basic)

<a name="step-7"></a>

<!--ENDOFSECTION-->

## <a name="step-7-upgrade-users-to-teams"></a>Etapa 7. Atualize os usuários para o Teams!

*(Dia da Atualização)*

Hoje é o dia em que sua organização atualiza oficialmente para o Teams como sua solução de comunicação e colaboração. No centro de administração do Microsoft Teams, ative a opção de atualização definindo o modo de coexistência como **Somente Equipes**. (No centro de administração, acesse **Configurações em** toda a organização  >  **Atualização do Teams**.) Os usuários receberão uma notificação em seu cliente do Skype for Business de que foram atualizados para o Teams.

Recomendamos que, após a atualização de todos, você envie um email acolhendo-os ao Teams.

**Recursos:**

- [Definir suas configurações de coexistência e atualização](setting-your-coexistence-and-upgrade-settings.md)
- [Exemplo de email: bem-vindo aos usuários do Teams](upgrade-emails-surveys.md#step-7-email)

[Retornar ao topo](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-8"></a>

## <a name="step-8-monitor-teams-usage-against-your-baseline"></a>Etapa 8. Monitorar o uso do Teams em relação à linha de base

*(Cerca de uma ou duas semanas após a atualização)*

O ajuste a uma nova tecnologia pode levar algum tempo. Verifique o uso para verificar se os usuários estão usando o Teams no mesmo nível — ou maior — como fizeram com o Skype for Business. Entre com usuários que não estão usando o Teams nos níveis esperados.

**Recursos:**

- [Consulte dados de uso](https://portal.office.com/AdminPortal/Home#/reportsUsage)

[Retornar ao topo](#about-upgrade-basic)

<a name="step-9"></a>

<!--ENDOFSECTION-->

## <a name="step-9-measure-user-satisfaction"></a>Etapa 9. Medir a satisfação do usuário

*(Cerca de uma ou duas semanas após a atualização)*

A satisfação dos funcionários pode influenciar a produtividade, a retenção e, em última análise, os resultados dos negócios. Entre em contato com seus usuários para avaliar o sentimento do usuário sobre a atualização e sua satisfação com o Teams.

**Recursos:**

- [Exemplo de email: fazer check-in com usuários](upgrade-emails-surveys.md#step-9-email), além [de pesquisas de usuário](upgrade-emails-surveys.md#step-9-surveys)

[Retornar ao topo](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-10"></a>

## <a name="step-10-maximize-your-roi-with-teams"></a>Etapa 10. Maximizar seu ROI com o Teams

*(Em andamento)*

Depois que os usuários se sentem confortáveis com mensagens de IM (chat) e reuniões no Teams, incentive-os a estender seu caso de uso usando a colaboração do Teams e a integração de aplicativos, otimizando verdadeiramente sua nova solução e maximizando um retorno sobre seu investimento.

**Recursos:**

- [Exemplo de email: incentivar os usuários a explorar ainda mais o Teams](upgrade-emails-surveys.md#step-10-email)

[Retornar ao topo](#about-upgrade-basic)