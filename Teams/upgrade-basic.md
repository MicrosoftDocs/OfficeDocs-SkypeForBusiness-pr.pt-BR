---
title: Lista de verificação de atualização| Atualização do Skype Business para o Teams | Etapas básicas
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Siga este plano de ação de dez etapas acelerada para fazer a transição de uma configuração Skype for Business básica para a configuração do Microsoft Teams.
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
ms.openlocfilehash: aab5ff20ef241b3e80eaf7909fb960eff94bfbe8
ms.sourcegitcommit: 79ada2140b110239deff96e4854ebd5dd9b77881
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2022
ms.locfileid: "66606020"
---
# <a name="upgrade-basic"></a>Atualizar Básico

<a name="about-upgrade-basic"></a>

Projetada para organizações menores ou aquelas que usam o Skype for Business Online somente para mensagens instantâneas (chat) e reuniões, a lista de verificação Atualizar Básico é um plano de ação acelerada que inclui atividades básicas, recomendadas e recursos associados para implementar uma mudança bem-sucedida do Skype for Business para o Teams.

Essas dez etapas fáceis fornecem tudo o que você precisa para uma atualização bem-sucedida. Eles foram projetados para serem concluídos em cerca de 30 a 45 dias, mas você deve ajustar as datas de conclusão da tarefa com base no agendamento de atualização da sua organização.

> [!IMPORTANT]
> Skype for Business Online foi desativado em 31 de julho de 2021. Para maximizar a realização dos benefícios e garantir que sua organização tenha tempo adequado para implementar a atualização, recomendamos que você comece hoje sua jornada para o Microsoft Teams.

O que acontece com Skype for Business após a atualização? Depois que seus usuários forem atualizados para o Teams (modo **Apenas Teams**):

- O Skype for Business cliente está desabilitado e todos os chats e chamadas vão para o Teams. Observe que isso não desinstalará o cliente em suas áreas de trabalho.
- Todas Skype for Business que foram agendadas antes da atualização funcionam conforme projetado, mas todas as novas reuniões são agendadas no Teams. O Skype for Business plug-in não estará mais disponível no Outlook. 
- Se os usuários tentarem entrar no Skype for Business, eles receberão uma notificação do cliente de que foram atualizados para o Teams.
- Os usuários precisam desinstalar manualmente Skype for Business cliente em seus dispositivos móveis.

Confira nossas [perguntas frequentes](./faq-journey.yml) sobre a atualização.

Não está familiarizado com o Teams? [Leia sobre](https://products.office.com/microsoft-teams/group-chat-software) como o Teams reúne conversas, reuniões, arquivos, aplicativos do Office e integrações de terceiros, fornecendo um único hub para trabalho em equipe no Microsoft 365 e Office 365.

<!--ENDOFSECTION-->

<a name="step-1"></a>

## <a name="step-1-notify-your-key-stakeholders"></a>Etapa 1. Notificar seus principais stakeholders

*(Cerca de quatro a seis semanas antes da atualização)*

Os líderes seniores são assumentesáveis pelo sucesso da empresa; certifique-se de mantê-los no saber sobre as alterações de tecnologia. Como é possível que nem todos receberam ou leram a notificação de qualificação de atualização, você precisa informar seus stakeholders (por exemplo, CEO, profissionais de TI, marketing e clientes potenciais de assistência técnica) antes de começar a planejar a atualização.

**Recursos:**

- [Email de exemplo: comunicação de stakeholders](upgrade-emails-surveys.md#step-1-email)

[Retornar ao topo](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-2"></a>

## <a name="step-2-prepare-your-organization-for-teams"></a>Etapa 2. Preparar sua organização para o Teams

*(Cerca de quatro a seis semanas antes da atualização)*

O Teams oferece Skype for Business funcionalidade compatível, como mensagens instantâneas (chat) e reuniões, mas também pode fazer muito mais. Como um verdadeiro hub para trabalho em equipe, o Teams permite que os grupos de trabalho gerenciem projetos, arquivos, conversas e aplicativos em um único local. Por padrão, o Microsoft Teams é ativado para todas as organizações. Decida como sua organização usará o Teams e configurará seu ambiente para sucesso. 

> [!Note]
> Como um cliente Skype for Business existente, sua infraestrutura de rede atual provavelmente já está configurada para o Teams. Para confirmar isso, você pode seguir as diretrizes de "Planejamento técnico completo" vinculadas abaixo (isso é opcional).

**Recursos:**

- [Visão geral do Teams](Teams-overview.md)
- [Introdução ao Microsoft Teams](get-started-with-teams-quick-start.md)

[Retornar ao topo](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-3"></a>

## <a name="step-3-know-your-skype-for-business-users"></a>Etapa 3. Conheça seus Skype for Business usuários

*(Cerca de quatro semanas antes da atualização)*

Os usuários que são profundamente adotados Skype for Business podem precisar de um pouco mais de tempo ou assistência para fazer a transição para o Teams. Reserve um tempo para examinar o uso atual Skype for Business para identificar os principais usuários que precisam de suporte adicional e estabelecer uma linha de base de uso que você pode acompanhar em relação aos números pós-atualização.

**Recursos:**

- [Relatórios do Microsoft 365 no centro de administração](/microsoft-365/admin/activity-reports/activity-reports)

[Retornar ao topo](#about-upgrade-basic)

<a name="step-4"></a>

<!--ENDOFSECTION-->

## <a name="step-4-notify-your-users-that-theyll-be-upgrading-from-skype-for-business-to-teams"></a>Etapa 4. Notifique os usuários de que eles serão atualizados do Skype for Business para o Teams

*(Cerca de duas a três semanas antes da atualização)*

Fornecer um aviso amplo aos usuários dará tempo para que eles se familiarizem com o Teams sem afetar negativamente sua produtividade, resultando em uma experiência de usuário mais positiva. Envie uma comunicação para dizer a eles o que está mudando, por que ela está mudando e como eles podem se preparar para isso.

> [!Note]
> Se necessário, você pode habilitar o Teams para seus usuários por meio Centro de administração do Microsoft 365 no momento.

**Recursos:**

- [Gerenciar as configurações do Microsoft Teams para sua organização](enable-features-office-365.md)
- [Email de exemplo: comunicado aos usuários sobre Skype for Business](upgrade-emails-surveys.md#step-4-email)

[Retornar ao topo](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-5"></a>

## <a name="step-5-activate-the-user-upgrade-notification"></a>Etapa 5. Ativar a notificação de atualização do usuário

*(Cerca de uma semana antes da atualização)*

Mantenha a dinâmica de atualização habilitando a notificação de atualização do usuário por meio do portal de administração, fornecendo um alerta visual no cliente do Skype for Business que os usuários estão sendo atualizados do Skype for Business para o Teams.

**Recursos:**

- [Definir suas configurações de coexistência e atualização](setting-your-coexistence-and-upgrade-settings.md)

[Retornar ao topo](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-6"></a>

## <a name="step-6-remind-your-users-that-theyll-be-upgrading-from-skype-for-business-to-teams"></a>Etapa 6. Lembre os usuários de que eles serão atualizados do Skype for Business para o Teams

*(Cerca de cinco dias antes da atualização)*

Os usuários estão ocupados com suas responsabilidades diárias. Lembrá-los da atualização pendente ajudará a garantir que eles se lembrem de seguir as etapas necessárias para se preparar para o Teams. Esse é o momento perfeito para lembrar os usuários sobre o treinamento disponível e como começar a usar o Teams.

**Recursos:**

- [Email de exemplo: lembrar os usuários de começar a usar o Teams](upgrade-emails-surveys.md#step-6-email)

[Retornar ao topo](#about-upgrade-basic)

<a name="step-7"></a>

<!--ENDOFSECTION-->

## <a name="step-7-upgrade-users-to-teams"></a>Etapa 7. Atualize os usuários para o Teams!

*(Dia da Atualização)*

Hoje é o dia em que sua organização atualiza oficialmente para o Teams como sua solução de comunicação e colaboração. No centro de administração do Microsoft Teams, ative a opção de atualização definindo o modo de coexistência como **Somente Teams**. (No centro de administração, vá para o **Teams** >  **Configurações de atualização do Teams**.) Os usuários receberão uma notificação Skype for Business cliente que foram atualizados para o Teams.

Recomendamos que, depois que todos forem atualizados, você envie um email acolhendo-os ao Teams.

**Recursos:**

- [Definir suas configurações de coexistência e atualização](setting-your-coexistence-and-upgrade-settings.md)
- [Email de exemplo: bem-vindo aos usuários do Teams](upgrade-emails-surveys.md#step-7-email)

[Retornar ao topo](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-8"></a>

## <a name="step-8-monitor-teams-usage-against-your-baseline"></a>Etapa 8. Monitorar o uso do Teams em relação à linha de base

*(Cerca de uma ou duas semanas após a atualização)*

Ajustar-se a uma nova tecnologia pode levar algum tempo. Verifique o uso para verificar se os usuários estão usando o Teams no mesmo nível ou superior, como fizeram com o Skype for Business. Faça check-in com usuários que não estão usando o Teams nos níveis esperados.

**Recursos:**

- [Ver dados de uso](https://portal.office.com/AdminPortal/Home#/reportsUsage)

[Retornar ao topo](#about-upgrade-basic)

<a name="step-9"></a>

<!--ENDOFSECTION-->

## <a name="step-9-measure-user-satisfaction"></a>Etapa 9. Medir a satisfação do usuário

*(Cerca de uma ou duas semanas após a atualização)*

A satisfação dos funcionários pode influenciar a produtividade, a retenção e, em última análise, os resultados dos negócios. Entre em contato com seus usuários para avaliar o sentimento do usuário sobre a atualização e sua satisfação com o Teams.

**Recursos:**

- [Email de exemplo: fazer check-in com usuários](upgrade-emails-surveys.md#step-9-email), além [de pesquisas de usuário](upgrade-emails-surveys.md#step-9-surveys)

[Retornar ao topo](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-10"></a>

## <a name="step-10-maximize-your-roi-with-teams"></a>Etapa 10. Maximizar seu ROI com o Teams

*(Em andamento)*

Depois que os usuários se familiarizarem com mensagens instantâneas (chat) e reuniões no Teams, incentive-os a estender seu caso de uso usando a colaboração e a integração de aplicativos do Teams, otimizando verdadeiramente sua nova solução e maximizando um retorno sobre seu investimento.

**Recursos:**

- [Email de exemplo: incentivar os usuários a explorar ainda mais o Teams](upgrade-emails-surveys.md#step-10-email)

[Retornar ao topo](#about-upgrade-basic)
