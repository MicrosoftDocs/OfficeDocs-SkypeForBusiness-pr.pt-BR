---
title: Processo de atualização de equipes
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 05/08/2019
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: annaray
search.appverid: MET150
description: Saiba como o cliente de desktop equipes é atualizado.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 04b7d1e66905e7859139605b90b3093a48e8afbd
ms.sourcegitcommit: b072148ea13f4d4f6035204a48bedd287fb90ebd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/08/2019
ms.locfileid: "33829092"
---
# <a name="teams-update-process"></a>Processo de atualização de equipes

O aplicativo da Web de equipes é atualizado semanal.

Atualizações de cliente de desktop equipes sejam liberadas cada duas semanas após rigorosos testes internos e validação por meio de nosso programa de adoção de tecnologia (toque). Isso geralmente ocorre em uma terça-feira. Se uma atualização crítica for necessária, equipes irá ignorar essa agenda e liberar a atualização assim que estiver disponível.

Cliente de desktop do próprio atualiza automaticamente. Verificações de equipes para atualiza cada poucas horas em segundo plano, a baixa e aguarda até que o computador ficar ocioso antes silenciosamente instalando a atualização.

Os usuários podem baixar também manualmente as atualizações ao clicar em **Verificar se há atualizações** no menu suspenso de **perfil** no canto superior direito do aplicativo. Se houver uma atualização disponível, ele será baixado e instalado silenciosamente quando o computador estiver ocioso.

Os usuários precisam estar conectado para atualizações sejam baixados.

## <a name="what-about-updates-to-office-365-proplus"></a>E sobre atualizações do Office 365 ProPlus?

As equipes é instalado por padrão com as novas instalações do Office 365 ProPlus, conforme descrito em [Implantar equipes da Microsoft com o Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/teams-install). 

As equipes segue seu próprio processo de atualização, conforme descrito acima e não o processo de atualização para os outros aplicativos de escritórios, como Word e Excel.

## <a name="what-about-updates-to-teams-on-vdi"></a>E quanto a atualizações a equipes de VDI?

Clientes de equipes em Virtual Desktop Infrastructure (VDI) não são atualizados automaticamente a maneira que os clientes não - VDI equipes. Você precisa atualizar a imagem da VM instalando um novo MSI, conforme descrito nas instruções para [Instalar equipes em VDI](https://docs.microsoft.com/microsoftteams/teams-for-vdi#install-teams-on-vdi). Você deve desinstalar a versão atual para atualizar para uma versão mais recente.

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a>Pode admins implantar as atualizações em vez de equipes atualização automática?

As equipes não dá admins a capacidade de implantar atualizações por meio de qualquer mecanismo de entrega.
