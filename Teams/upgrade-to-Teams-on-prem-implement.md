---
title: Atualize para o Teams a partir de uma implantação local do Skype for Business-Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Atualização do Skype for Business para o Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: bec5c2b10dc2e09092cd7c26284c04868982e287
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533598"
---
# <a name="implement-your-upgrade-from-skype-for-business-to-teams-mdash-for-it-administrators"></a>Implementar a atualização do Skype for Business para o Teams &mdash; para administradores de ti

Este artigo descreve como implementar a atualização. Este artigo é o quinto de vários que descrevem os conceitos de atualização e a implementação para administradores de ti.  

- [Visão geral](upgrade-to-teams-on-prem-overview.md)
- [Métodos de atualização](upgrade-to-teams-on-prem-upgrade-methods.md)
- [Ferramentas para gerenciar a atualização](upgrade-to-teams-on-prem-tools.md)
- [Considerações adicionais sobre organizações com o Skype for Business no local](upgrade-to-teams-on-prem-considerations.md)
- **Implementar a atualização** (este artigo)
- [Considerações sobre PSTN (rede telefônica pública comutada)](upgrade-to-teams-on-prem-pstn-considerations.md)

Além disso, os seguintes artigos descrevem conceitos importantes de atualização e comportamentos de coexistência:

- [Coexistência de Teams e Skype for Business](upgrade-to-teams-on-prem-coexistence.md)
- [Modos de coexistência-referência](migration-interop-guidance-for-teams-with-skype.md)
- [Experiência e conformidade do cliente do Teams a modos de coexistência](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="upgrade-options"></a>Opções de atualização

Esta seção descreve como implementar a atualização usando uma das seguintes opções de atualização:

- [Atualização de recursos sobrepostos (usando o modo de ilhas)](#overlapping-capabilities-upgrade-using-islands-mode)
- [Uma atualização de recursos selecionados para uma organização que ainda não começou a usar o Teams](#a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams)
- [Uma atualização de recursos de seleção para uma organização que já está usando equipes no modo de ilhas](#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode)

Se precisar de mais informações sobre as opções, verifique se você já leu os [métodos de atualização](upgrade-to-teams-on-prem-upgrade-methods.md).

## <a name="overlapping-capabilities-upgrade-using-islands-mode"></a>Atualização de recursos sobrepostos (usando o modo de ilhas)

Para a opção de atualização de recursos sobrepostos:

- Considere esta opção se você pode fazer uma atualização rápida para a sua organização geral.  Como há potencial risco de confusão para os usuários finais executarem ambos os clientes, é melhor minimizar o período de tempo durante o qual os usuários devem executar ambos os clientes. Você deve garantir que os usuários saibam que executar os dois clientes.

- Essa opção é o modelo de caixa de saída e não exige ação do administrador para começar a usar o Microsoft Teams, exceto para atribuir a licença do Microsoft 365 ou do Office 365. Se seus usuários já têm o Skype for Business Online, você pode já estar nesse modelo.

- Pode ser difícil sair do modo de recursos sobrepostos e mover para TeamsOnly. Como os usuários atualizados só se comunicam via Teams, qualquer outro usuário na organização que se comunique com esse usuário deve estar usando o Microsoft Teams.  Se você tiver usuários que não começaram a usar o Teams, eles serão expostos a mensagens ausentes. Além disso, eles não verão os usuários do TeamsOnly online no Skype for Business. Algumas organizações optam por fazer uma atualização em todo o locatário usando a política global do locatário para evitar isso, no entanto, isso requer o planejamento antecipado, bem como aguardar até que todos os usuários estejam prontos para serem atualizados.


## <a name="a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams"></a>Uma atualização de recursos selecionados para uma organização que ainda não começou a usar o Teams

Se a sua organização ainda não tem usuários ativos no Teams, a primeira etapa é definir a política padrão de todo o locatário do TeamsUpgradePolicy para um dos modos do Skype for Business, por exemplo, SfbWithTeamsCollab.  Os usuários que ainda não começaram a usar o Teams não notarão diferença no comportamento. No entanto, definir essa política no nível do locatário torna possível iniciar a atualização dos usuários para o modo TeamsOnly e garante que os usuários atualizados ainda possam se comunicar com usuários não atualizados.  Depois de identificar os usuários piloto, você pode atualizá-los para o TeamsOnly.  Se eles estiverem locais, use move-CsUser. Se estiverem online, basta atribuí-los ao modo TeamsOnly usando Grant-CsTeamsUpgradePolicy. Por padrão, todas as reuniões do Skype for Business agendadas por esses usuários serão migradas para o Microsoft Teams.

Veja a seguir os comandos principais:

1. Defina o padrão do locatário-Wide para mode SfbWithTeamsCollab da seguinte maneira:

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
   ```

2. Atualize os usuários piloto para o TeamsOnly da seguinte maneira:

   - Para um usuário que está online:

     ```PowerShell
     Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $username 
     ```

   - Para um usuário local:

     ```PowerShell
     Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
     ```

Observações
 
- Em vez de definir a política de todo o locatário como SfbWithTeamsCollab, você pode defini-la como SfbWithTeamsCollabAndMeetings. Isso faz com que todos os usuários agendem todas as novas reuniões no Teams.
- `Move-CsUser` é um cmdlet nas ferramentas locais. O `MoveToTeams` switch requer o Skype for Business server 2019 ou o Skype for Business server 2015 com o CU8 ou posterior. Se estiver usando uma versão anterior, você pode primeiro mover o usuário para o Skype for Business Online e, em seguida, conceder o modo TeamsOnly a esse usuário.
- Por padrão, as reuniões do Skype for Business são migradas para o Microsoft Teams durante a atualização para o modo TeamsOnly ou ao atribuir o modo de SfbWithTeamsCollabAndMeetings.  

O diagrama a seguir mostra a atualização das fases conceituais de recursos selecionados para uma organização sem o uso anterior do teams. A altura das barras representa o número de usuários. Durante qualquer fase da atualização, todos os usuários podem se comunicar uns com os outros.  Os usuários do Skype for Business se comunicam com usuários do TeamsOnly usando a interoperabilidade e vice-versa. Os usuários no modo de ilhas devem ter certeza de que devem executar os dois clientes.

![Diagrama mostrando a atualização de recursos de seleção sem uso anterior do teams](media/teams-upgrade-1.png)


## <a name="a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode"></a>Uma atualização de recursos de seleção para uma organização que já está usando equipes no modo de ilhas

Se alguns usuários da sua organização estiverem usando ativamente o Microsoft Teams no modo de ilhas, provavelmente não deseja remover a funcionalidade de usuários existentes. Portanto, uma etapa adicional é necessária antes de alterar a política de todo o locatário. A solução é "avô" esses usuários existentes do Microsoft Teams no modo de ilhas, antes de definir a política de todo o locatário como SfbWithTeamsCollab.  Depois de fazer isso, você poderá prosseguir com a implantação da maneira acima, no entanto, terá dois grupos de usuários que estão indo para o TeamsOnly: os usuários que estavam ativos no Teams estarão no modo de ilhas e os usuários restantes estarão no modo SfbWithTeamsCollab. Você pode mover progressivamente esses usuários para o modo TeamsOnly.

1. Encontre os usuários ativos no Teams da seguinte maneira:

   1. No centro de administração do Microsoft 365, na navegação à esquerda, vá para relatórios e use o uso. 
   2. Na lista suspensa "selecionar um relatório", escolha Microsoft Teams e, em seguida, atividade do usuário. Isso fornecerá uma tabela exportável de usuários que já estão ativos no Teams. 
   3. Clique em exportar, abrir Excel e filtrar para mostrar somente os usuários que estão ativos no Teams.

2. Para cada usuário do Active Teams encontrado na etapa 1, atribua o modo de ilhas no PowerShell no PowerShell remoto. Isso permite que você vá para a próxima etapa e assegure-se de que não altere a experiência do usuário.  

   ```PowerShell
   $users=get-content “C:\MyPath\users.txt” 
    foreach ($user in $users){ 
    Grant-CsTeamsUpgradePolicy -identity $user -PolicyName Islands} 
   ```

3. Defina a política de todo o locatário como SfbWithTeamsCollab:

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Global -PolicyName SfbWithTeamsCollab 
   ```

4. Atualizar os usuários selecionados para o modo TeamsOnly. Você pode optar por atualizar os usuários no modo de ilhas ou no modo SfbWithTeamsCollab, embora você queira priorizar a atualização dos usuários no modo ilhas primeiro para minimizar o potencial de confusão que podem surgir quando os usuários estiverem no modo de ilhas.   

   Para usuários hospedados no Skype for Business Online:  

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams 
   ```

   Para os usuários hospedados no Skype for Business Server no local:  

   ```PowerShell
   Move-CsUser -Identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
   ```

O diagrama a seguir mostra as fases conceituais de uma transição de recursos selecionados em que há usuários de ilhas ativas no início. A altura das barras representa o número de usuários. Durante qualquer fase da atualização, todos os usuários podem se comunicar uns com os outros.  Os usuários do Skype for Business se comunicam com usuários do TeamsOnly usando a interoperabilidade e vice-versa. 


![Diagrama mostrando a atualização de recursos de seleção com usuários ativos no modo de ilhas](media/teams-upgrade-2.png)

   



## <a name="related-links"></a>Links relacionados

[Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business](migration-interop-guidance-for-teams-with-skype.md) 

[Configurar a conectividade híbrida entre o Skype for Business Server e o Microsoft 365 ou o Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Mover os usuários entre um ambiente local e a nuvem](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Definir suas configurações de coexistência e atualização](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Usando o Meeting Migration Service (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

