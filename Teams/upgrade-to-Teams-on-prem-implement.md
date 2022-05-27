---
title: Estratégias de atualização para administradores de TI
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: O artigo é para administradores de TI e descreve estratégias para implementar sua atualização de Skype for Business para Teams.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f403b12ffc8cabbfebe8a30268eb3e6dad468f32
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681732"
---
# <a name="upgrade-strategies-for-it-administrators"></a>Estratégias de atualização para administradores de TI

![Estágios do percurso de atualização, com ênfase no estágio implantação e implementação.](media/upgrade-banner-deployment.png "Estágios do percurso de atualização, com ênfase no estágio implantação e implementação")

Este artigo destina-se aos administradores de TI que desejam implementar a atualização para Teams de Skype for Business.

Antes de implementar sua atualização, recomendamos os seguintes artigos que descrevem conceitos importantes de atualização e comportamentos de coexistência:

- [Entender Microsoft Teams e Skype for Business coexistência e interoperabilidade](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Modos de coexistência – Referência](migration-interop-guidance-for-teams-with-skype.md)
- [Experiência e conformidade do cliente do Teams a modos de coexistência](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="upgrade-options"></a>Opções de atualização

Esta seção descreve como implementar sua atualização usando uma das seguintes opções de atualização:

- [Atualização de funcionalidades sobrepostas (usando o modo Ilhas)](#overlapping-capabilities-upgrade-using-islands-mode)
- [Uma atualização de recursos selecionados para uma organização que ainda não começou a usar o Teams](#a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams)
- [Uma atualização de recursos selecionados para uma organização que já está usando Teams no modo Ilhas](#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode)

Se precisar de mais informações sobre as opções, verifique se você já leu Escolher seu percurso de atualização de Skype for Business [para Teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md).

## <a name="overlapping-capabilities-upgrade-using-islands-mode"></a>Atualização de funcionalidades sobrepostas (usando o modo Ilhas)

Para a opção de atualização de recursos sobrepostos:

- Considere essa opção se você puder fazer uma atualização rápida para sua organização geral.  Como há um risco potencial de confusão para os usuários finais com a execução de ambos os clientes, é melhor minimizar o período durante o qual os usuários devem executar ambos os clientes. Você deve garantir que os usuários saibam executar ambos os clientes.

- Essa opção é o modelo fora da caixa e não requer ação de administrador para começar a usar o Teams, exceto para atribuir a licença de Microsoft 365 ou Office 365. Se os usuários já Skype for Business Online, talvez você já esteja nesse modelo.

- Pode ser desafiador sair do modo de sobreposição de recursos e mudar para o TeamsOnly. Como os usuários atualizados só se comunicam Teams, qualquer outro usuário na organização que se comunica com esse usuário deve estar usando Teams.  Se você tiver usuários que não começaram a usar Teams, eles serão expostos a mensagens ausentes. Além disso, eles não verão os usuários do TeamsOnly online no Skype for Business. Algumas organizações optam por fazer uma atualização em todo o locatário usando a política global de locatário para evitar isso, no entanto, isso requer planejamento antecipado, bem como aguardar até que todos os usuários estejam prontos para serem atualizados.

## <a name="a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams"></a>Uma atualização de recursos selecionados para uma organização que ainda não começou a usar o Teams

Se sua organização ainda não tiver nenhum usuário ativo no Teams, a primeira etapa será definir a política padrão em todo o locatário para TeamsUpgradePolicy como um dos modos Skype for Business, por exemplo, SfbWithTeamsCollab.  Os usuários que ainda não começaram a usar Teams não perceberão nenhuma diferença no comportamento. No entanto, definir essa política no nível do locatário possibilita iniciar a atualização de usuários para o modo TeamsOnly e garante que os usuários atualizados ainda possam se comunicar com usuários não atualizados.  Depois de identificar os usuários piloto, você poderá atualizá-los para o TeamsOnly.  Se eles estiverem no local, use Move-CsUser. Se eles estiverem online, basta atribuí-los ao modo TeamsOnly usando Grant-CsTeamsUpgradePolicy. Por padrão, todas as Skype for Business agendadas por esses usuários serão migradas para Teams.

A seguir estão os principais comandos:

1. Defina o padrão de todo o locatário para o modo SfbWithTeamsCollab da seguinte maneira:

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
   ```

2. Atualize os usuários piloto para o TeamsOnly da seguinte maneira:

   - Para um usuário que está online:

     ```PowerShell
     Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $username
     ```

   - Para um usuário que está no local:

     ```PowerShell
     Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred
     ```

**Observações**:

- Em vez de definir a política em todo o locatário como SfbWithTeamsCollab, você pode defini-la como SfbWithTeamsCollabAndMeetings. Isso faz com que todos os usuários agendem todas as novas reuniões no Teams.
- Por padrão, Skype for Business reuniões são migradas para o Teams ao atualizar para o modo TeamsOnly ou ao atribuir o modo SfbWithTeamsCollabAndMeetings.

> [!NOTE]
> Em preparação para a próxima desativação do Skype for Business Online, a Microsoft simplifica a maneira como as organizações migram para Teams. Não é mais necessário especificar a `-MoveToTeams` opção para `Move-CsUser` mover os usuários diretamente do local diretamente para o TeamsOnly. Anteriormente, se essa opção não fosse especificada, os usuários iam de ser hospedados no Skype for Business Server local para o Skype for Business Online e seu modo permanece inalterado. Agora, ao mover um usuário do local para a nuvem com o modo TeamsOnly, os usuários são atribuídos `Move-CsUser`automaticamente ao modo TeamsOnly e suas reuniões locais são automaticamente convertidas em reuniões de Teams, `-MoveToTeams switch had been specified`como se, independentemente de a opção ser realmente especificada. Esse comportamento está disponível em todas as versões do Skype For Business Server e do Lync Server 2013 (que nunca tiveram suporte para `-MoveToTeams`).

O diagrama a seguir mostra as fases conceituais de atualização de recursos selecionados para uma organização sem uso anterior de Teams. A altura das barras representa o número de usuários. Durante qualquer fase da atualização, todos os usuários podem se comunicar entre si.  Skype for Business se comunicam com usuários do TeamsOnly usando Interoperabilidade e vice-versa. Os usuários no modo Ilhas devem ter certeza de executar ambos os clientes.

![Diagrama mostrando a atualização de recursos selecionados sem nenhum uso anterior Teams.](media/teams-upgrade-1.png)

## <a name="a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode"></a>Uma atualização de recursos selecionados para uma organização que já está usando Teams no modo Ilhas

Se alguns usuários em sua organização estão usando ativamente Teams no modo Ilhas, você provavelmente não deseja remover a funcionalidade de usuários existentes. Portanto, uma etapa extra é necessária antes de alterar a política em todo o locatário. A solução é "avô" desses usuários Teams existentes no modo Ilhas, antes de definir a política de todo o locatário como SfbWithTeamsCollab.  Depois de fazer isso, você pode continuar com a implantação como acima, no entanto, você terá dois grupos de usuários que estão migrando para o TeamsOnly: os usuários que estavam ativos no Teams estarão no modo Ilhas e os usuários restantes estarão no modo SfbWithTeamsCollab. Você pode mover progressivamente esses usuários para o modo TeamsOnly.

1. Localize os usuários que estão ativos Teams a seguir:

   1. No Centro de administração do Microsoft 365, na navegação à esquerda, vá para Relatórios e, em seguida, Uso.
   2. Na lista suspensa "Selecionar um relatório", escolha Microsoft Teams e, em seguida, Atividade do Usuário. Isso fornecerá uma tabela exportável de usuários que foram ativos no Teams.
   3. Clique em Exportar, Excel e filtre para mostrar somente os usuários que estão ativos no Teams.

2. Para cada usuário Teams ativo encontrado na etapa 1, atribua-o ao modo Ilhas no PowerShell remoto. Isso permite que você vá para a próxima etapa e garante que você não altere a experiência do usuário.

   ```PowerShell
   $users=get-content "C:\MyPath\users.txt"
    foreach ($user in $users){
    Grant-CsTeamsUpgradePolicy -identity $user -PolicyName Islands}
   ```

3. Defina a política de todo o locatário como SfbWithTeamsCollab:

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Global -PolicyName SfbWithTeamsCollab
   ```

4. Atualize os usuários selecionados para o modo TeamsOnly. Você pode optar por atualizar os usuários no modo Ilhas ou no modo SfbWithTeamsCollab, embora você queira priorizar a atualização dos usuários no modo Ilhas primeiro para minimizar o potencial de confusão que pode surgir quando os usuários estão no modo Ilhas.

   Para usuários hospedados no Skype for Business Online:

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams
   ```

   Para usuários hospedados Skype for Business Server local:

   ```PowerShell
   Move-CsUser -Identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred
   ```

O diagrama a seguir mostra as fases conceituais de uma transição de recursos selecionados em que há usuários ativos das Ilhas no início. A altura das barras representa o número de usuários. Durante qualquer fase da atualização, todos os usuários podem se comunicar entre si.  Skype for Business se comunicam com usuários do TeamsOnly usando interoperabilidade e vice-versa.

![Diagrama mostrando a atualização de recursos selecionados com usuários ativos no modo Ilhas.](media/teams-upgrade-2.png)

## <a name="related-links"></a>Links relacionados

[Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business](migration-interop-guidance-for-teams-with-skype.md)

[Configurar a conectividade híbrida entre Skype for Business Server e Microsoft 365 ou Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Mover os usuários entre um ambiente local e a nuvem](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Definir suas configurações de coexistência e atualização](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy)

[Usando o Meeting Migration Service (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
