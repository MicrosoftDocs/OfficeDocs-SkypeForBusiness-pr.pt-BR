---
title: Gerenciar a avaliação de linha de frente Teams
author: daisyfell
ms.author: daisyfeller
ms.reviewer: samanro
manager: pamgreen
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Saiba como configurar uma avaliação de 90 dias Teams trabalhadores de linha de frente para sua organização.
ms.localizationpriority: medium
ms.collection:
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 098cb4cd84616a9b26ea7df5c1451219fd5b5f0e
ms.sourcegitcommit: 8ce73ea99be607f5cdccb22a5366bc96e8fb09c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2022
ms.locfileid: "65758289"
---
# <a name="manage-the-frontline-trial-in-teams"></a>Gerenciar a avaliação de linha de frente Teams

> [!NOTE]
> Essa experiência de avaliação estará disponível em breve. Você pode verificar quando isso está disponível para sua organização procurando uma mensagem no Centro de mensagens em [](https://go.microsoft.com/fwlink/p/?linkid=2070717) seu Administração Microsoft 365 central.

A experiência de avaliação do Microsoft Teams Frontline permite que os usuários em sua organização que estão no Teams iniciem uma experiência de Teams para toda a equipe de linha de frente, desde que os outros membros estejam em Azure Active Directory (Azure AD). Você pode desabilitar esse recurso para usuários em sua organização usando o [módulo AllowSelfServicePurchase do PowerShell](/microsoft-365/commerce/subscriptions/allowselfservicepurchase-powershell).

## <a name="what-services-are-included"></a>Quais serviços estão incluídos

A avaliação inclui tudo na Microsoft 365 F3 [com](https://www.microsoft.com/microsoft-365/enterprise/f3) as seguintes exceções:

- A avaliação do Frontline inclui Exchange Foundation em vez de Exchange Quiosque. Os usuários podem estar sem outras Teams funcionalidades devido a essa alteração.

## <a name="eligibility"></a>Elegibilidade

> [!NOTE]
> Você pode verificar se sua organização faz parte do piloto de avaliação procurando um comunicado no Centro de mensagens [](https://go.microsoft.com/fwlink/p/?linkid=2070717) em seu Administração Microsoft 365 centro. Sua organização precisará fazer parte do piloto de avaliação para que os usuários iniciem ou participem de uma avaliação. Esta oferta não está disponível para clientes GCC, GCC High, DoD ou EDU.

A Avaliação de Linha de Frente pode acomodar um máximo de 300 usuários por avaliação.

Os usuários podem iniciar uma avaliação de linha de frente para sua equipe se:

- Ter uma licença ativa que dê a eles acesso a Teams.
- Ainda não iniciou uma avaliação de trabalho de linha de frente.

> [!IMPORTANT]
> Se o usuário que iniciou a avaliação sair da sua organização antes do término da avaliação, você como administrador precisará monitorar a avaliação, entrar com a equipe para ver quem está se beneficiando desses recursos e decidir quais usuários você precisará atualizar para uma licença paga.

Os usuários poderão participar de uma avaliação de trabalho de linha de frente se tiverem um endereço de email Azure Active Directory domínio gerenciado.

Os usuários podem participar se já iniciaram uma avaliação, mas não podem iniciar outra avaliação.

> [!NOTE]
> Os usuários sem acesso existente Teams podem ser adicionados apenas à equipe de avaliação no momento da criação da equipe. Os usuários Teams existentes ainda podem ser adicionados à avaliação após a criação da equipe.

## <a name="set-up-the-trial"></a>Configurar a avaliação

Os usuários qualificados podem iniciar uma Avaliação de Linha de Frente entrando no aplicativo Tarefas Teams do aplicativo Web ou da área [de trabalho](https://teams.microsoft.com/_#/apps/com.microsoft.teamspace.tab.planner/sections/mytasks). No momento, não há suporte para iniciar uma avaliação do Frontline por meio de dispositivos móveis. Quando uma avaliação for iniciada, toda a equipe receberá a licença de avaliação do Frontline automaticamente. Os usuários com licenças pagas existentes que lhes dão acesso ao Teams também receberão licenças de avaliação, mas manterão a funcionalidade de suas licenças existentes durante toda a avaliação e manterão suas licenças pagas existentes após o término da avaliação. O usuário que iniciou a avaliação receberá notificações por email durante a avaliação.

## <a name="manage-the-frontline-trials-experience"></a>Gerenciar a experiência de avaliações de linha de frente

Os administradores podem impedir que os usuários finais iniciam a avaliação do Frontline em sua organização usando o **módulo AllowSelfServicePurchase** do PowerShell. Isso é apenas para licenças de avaliação. [Saiba como usar o módulo AllowSelfServicePurchase do PowerShell](/microsoft-365/commerce/subscriptions/allowselfservicepurchase-powershell).

### <a name="manage-teams-for-users-who-have-the-frontline-trial-license"></a>Gerenciar Teams para usuários que têm a licença de avaliação do Frontline

Você pode gerenciar usuários que têm a licença de avaliação do Frontline da mesma forma que gerencia usuários que têm uma licença paga regular. Para mais informações, confira [Gerenciar as configurações do Teams da sua organização](/microsoftteams/manage-teams-overview).

### <a name="remove-a-trial-license"></a>Remover uma licença de avaliação

Você pode remover a licença de avaliação do Frontline por meio do PowerShell ou do Centro de administração do Microsoft 365.

[Saiba como remover com o PowerShell](/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell).

[Saiba como remover no centro de administração](/microsoft-365/admin/add-users/delete-a-user).

## <a name="upgrade-users-from-frontline-trial"></a>Atualizar usuários da avaliação do Frontline

Os usuários podem entrar em contato com você para solicitar licenças quando a avaliação estiver terminando. Você precisará de privilégios de administrador para atualizar seus usuários.

### <a name="when-to-upgrade"></a>Quando atualizar

Perto do final da avaliação de 90 dias, você precisará verificar com seus usuários para ver quem precisa continuar com uma licença paga. Certifique-se de fazer isso antes que a assinatura de Avaliação do Frontline expire para evitar qualquer interrupção nas experiências dos usuários.

> [!IMPORTANT]
> Se a licença de avaliação do Frontline terminar e um usuário não receber imediatamente uma licença que inclua Teams, ele perderá o acesso ao Teams. Após 30 dias, seus dados (arquivos, mensagens e muito mais) são excluídos. O usuário ainda existe no Azure Active Directory. Se uma nova licença for atribuída ao usuário para habilitar Teams funcionalidade dentro do período de 30 dias, todo o conteúdo no Teams ainda existirá.

### <a name="choose-an-upgrade-path"></a>Escolher um caminho de atualização

> [!TIP]
> A avaliação do Frontline baseia-se na [Microsoft 365 F3 licença](https://www.microsoft.com/microsoft-365/enterprise/f3).

Dependendo das assinaturas que sua organização tem atualmente, há três maneiras de atualizar de uma avaliação do Frontline para uma licença paga:

- **Atualizar uma assinatura Microsoft 365 existente.** Use essa opção se sua organização tiver assinaturas de outros produtos do Office que não incluem o Teams. Para obter mais informações, [consulte Atualizar para um plano diferente](/microsoft-365/commerce/subscriptions/upgrade-to-different-plan). Para ver os usuários ativos de uma assinatura existente, acesse **Usuários >** [Usuários ativos](https://go.microsoft.com/fwlink/p/?linkid=834822) no Centro de administração do Microsoft 365.

- **Adicionar usuários a uma assinatura Microsoft 365 existente.** Use essa opção se sua organização não tiver licenças pagas Teams suficientes para cobrir sua equipe de linha de frente. Para obter mais informações, consulte [Comprar ou remover licenças](/microsoft-365/commerce/licenses/buy-licenses). Para adicionar usuários a uma assinatura existente que já tenha licenças suficientes disponíveis, consulte [Mover usuários para uma assinatura diferente](/microsoft-365/commerce/subscriptions/move-users-different-subscription). Para ver os usuários ativos de uma assinatura existente, acesse **Usuários >** [Usuários ativos](https://go.microsoft.com/fwlink/p/?linkid=834822) no Centro de administração do Microsoft 365.

- **Comprar uma nova assinatura do Microsoft 365.** Use essa opção se sua organização não tiver assinaturas existentes para produtos do Office ou se sua organização quiser comprar uma assinatura diferente da assinatura existente para abranger usuários de linha de frente. Para obter mais informações, [consulte Microsoft 365 for frontline workers](https://www.microsoft.com/microsoft-365/enterprise/frontline).

Se você não tiver certeza para qual assinatura Microsoft 365 atualizar, [consulte Microsoft 365 for frontline workers](https://www.microsoft.com/microsoft-365/enterprise/frontline). Se você precisar de ajuda adicional para escolher uma assinatura ou se sua organização precisar de mais de 300 licenças, entre em contato com seu parceiro [Microsoft](https://www.microsoft.com/solution-providers/home) ou representante de conta Microsoft.

### <a name="assign-paid-licenses"></a>Atribuir licenças pagas

Para atribuir suas licenças recém-adquiridas, consulte [Atribuir licenças a usuários](/microsoft-365/admin/manage/assign-licenses-to-users).  

Depois de atribuir as novas licenças, cancele a atribuição das licenças do Teams Exploratory. Consulte [Cancelar a atribuição de licenças de usuários](/microsoft-365/admin/manage/remove-licenses-from-users), para obter mais informações.

## <a name="faq"></a>Perguntas frequentes

**Quanto tempo dura a avaliação** <br>
A avaliação do Frontline dura 90 dias.

**O que os administradores devem fazer no final da experiência de avaliação do Frontline de 90 dias?** <br>
No final da avaliação de 90 dias, você precisará verificar com seus usuários para ver quem precisa continuar com uma licença paga. Em seguida, você precisará atualizar [seus usuários](#upgrade-users-from-frontline-trial).

**O que acontece se o usuário que iniciou a avaliação sair da sua organização?** <br>
Você, como administrador, precisará monitorar a avaliação pelo restante do período de 90 dias e atualizar para licenças pagas para usuários que precisam delas quando a avaliação terminar.

**O que é a política de retenção de dados?** <br>
Você pode aprender sobre a retenção de dados nas [informações Microsoft 365 assinatura](/microsoft-365/commerce/subscriptions/what-if-my-subscription-expires?).

**E se um usuário encontrar um erro ao iniciar a avaliação do Frontline?** <br>
Verifique se sua organização, o usuário que está iniciando a avaliação e os usuários que estão sendo adicionados à avaliação atendem aos critérios [de qualificação](#eligibility).