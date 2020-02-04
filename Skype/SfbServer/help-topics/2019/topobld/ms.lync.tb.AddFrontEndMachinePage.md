---
title: Adicionar Máquina de Front End
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddFrontEndMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e7fe2522-1bd2-416a-9dbb-51cacea9c6e0
ROBOTS: NOINDEX, NOFOLLOW
description: Especifique o nome de domínio totalmente qualificado (FQDN) de cada computador que você deseja adicionar como um servidor front-end nesse pool. Depois de adicionar um computador à lista, você poderá atualizar o FQDN do computador ou removê-lo do pool em qualquer ocasião antes de publicar a topologia. Depois de publicar a topologia, alterar o FQDN exige a exclusão do servidor no construtor de topologia e, em seguida, adicionar um novo servidor ao pool com o novo FQDN. Para obter detalhes sobre como adicionar um pool de front-end à topologia, consulte definir e configurar um pool de front-end na documentação de implantação.
ms.openlocfilehash: a11042c8d91089e74ab1bacfc5206eb7d2fa3f67
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41689300"
---
# <a name="add-front-end-machine"></a>Adicionar Máquina de Front End

Especifique o nome de domínio totalmente qualificado (FQDN) de cada computador que você deseja adicionar como um servidor front-end nesse pool. Depois de adicionar um computador à lista, você poderá atualizar o FQDN do computador ou removê-lo do pool em qualquer ocasião antes de publicar a topologia. Depois de publicar a topologia, alterar o FQDN exige a exclusão do servidor no construtor de topologia e, em seguida, adicionar um novo servidor ao pool com o novo FQDN. Para obter detalhes sobre como adicionar um pool de front-end à topologia, consulte [definir e configurar um pool de front-end](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) na documentação de implantação.

> [!IMPORTANT]
> Observe que o construtor de topologias indica que você pode ter até 20 servidores front end em um pool. O número máximo de servidores com suporte é 12. Você pode ter até 20 servidores com monitoramento de estado definidos na malha, dos quais 12 podem estar ativos e online de uma só vez.


