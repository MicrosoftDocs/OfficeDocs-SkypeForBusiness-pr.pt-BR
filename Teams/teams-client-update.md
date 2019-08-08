---
title: Atualizações do Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 05/13/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: annaray
search.appverid: MET150
description: Saiba como o cliente de desktop Teams é atualizado.
appliesto:
- Microsoft Teams
ms.openlocfilehash: e0fe542c6df89946ad73f14cf9104f973e292aa3
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243837"
---
# <a name="teams-update-process"></a>Processo de atualização de equipes

O aplicativo Web Teams é atualizado semanalmente.

As atualizações do cliente de desktop do teams são lançadas a cada duas semanas após rigorosos testes internos e validação por meio do programa de adoção de tecnologia (toque). Geralmente, isso ocorre em uma terça-feira. Se for necessária uma atualização crítica, o Microsoft Teams ignorará esse cronograma e liberará a atualização assim que ela estiver disponível.

O cliente da área de trabalho é atualizado automaticamente. O Teams verifica se há atualizações a cada poucas horas nos bastidores, o descarrega e, em seguida, aguarda o computador ficar ocioso antes de instalar silenciosamente a atualização.

Os usuários também podem baixar manualmente as atualizações clicando em **verificar se há atualizações** no menu suspenso **perfil** no canto superior direito do aplicativo. Se houver uma atualização disponível, ela será baixada e instalada silenciosamente quando o computador estiver ocioso.

Os usuários precisam estar conectados para que as atualizações sejam baixadas. 

A partir de 9 de julho de 2019, as atualizações de cliente do teams usam uma menor largura de banda de rede durante a atualização. Isso é ativado por padrão e não requer nenhuma ação de administradores ou usuários.


## <a name="what-about-updates-to-office-365-proplus"></a>E quanto às atualizações do Office 365 ProPlus?

O Teams é instalado por padrão com novas instalações do Office 365 ProPlus, conforme descrito em [implantar o Microsoft Teams com o Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/teams-install). 

O Teams segue seu próprio processo de atualização, conforme descrito acima, e não o processo de atualização para os outros aplicativos do Office, como o Word e o Excel. Para saber mais, leia [visão geral dos canais de atualização do Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus)

## <a name="what-about-updates-to-teams-on-vdi"></a>E quanto às atualizações para o Microsoft Teams no VDI?

Os clientes do teams na Virtual Desktop Infrastructure (VDI) não são atualizados automaticamente da maneira como os clientes de equipes não VDI são. Você precisa atualizar a imagem da VM instalando um novo MSI conforme descrito nas instruções para instalar o Microsoft [Teams no VDI](https://docs.microsoft.com/microsoftteams/teams-for-vdi#install-teams-on-vdi). Você deve desinstalar a versão atual para atualizar para uma versão mais recente.

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a>Os administradores podem implantar atualizações em vez de atualizações automáticas do teams?

O Microsoft Teams não dá aos administradores a capacidade de implantar atualizações por meio de um mecanismo de entrega.
