---
title: Adicionar Máquina de Front End
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e7fe2522-1bd2-416a-9dbb-51cacea9c6e0
description: Especifique o FQDN (nome de domínio totalmente qualificado) de cada computador que você deseja adicionar como Servidor Front-End a esse pool. Após adicionar um computador à lista, você poderá atualizar o FQDN do computador ou removê-lo do pool a qualquer momento antes da publicação da topologia. Depois da publicação da topologia, a alteração do FQDN exigirá a exclusão do servidor do Construtor de Topologia e a adição de um novo servidor ao pool com o novo FQDN. Para obter detalhes sobre a adição de um pool de Front-Ends à topologia, consulte Define and Configure a Front End Pool, na documentação de Implantação.
ms.openlocfilehash: b100cfd933f19c87213fa48d4d030eda52e90dc8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119760"
---
# <a name="add-front-end-machine"></a>Adicionar Máquina de Front-end

Especifique o FQDN (nome de domínio totalmente qualificado) de cada computador que você deseja adicionar como Servidor Front-End a esse pool. Após adicionar um computador à lista, você poderá atualizar o FQDN do computador ou removê-lo do pool a qualquer momento antes da publicação da topologia. Depois da publicação da topologia, a alteração do FQDN exigirá a exclusão do servidor do Construtor de Topologia e a adição de um novo servidor ao pool com o novo FQDN. Para obter detalhes sobre a adição de um pool de Front-Ends à topologia, consulte [Define and Configure a Front End Pool](/previous-versions/office/lync-server-2013/lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server), na documentação de Implantação.

> [!IMPORTANT]
> Observe que o Construtor de Topologias indica que você pode ter até 20 Servidores Front-End em um pool. O número máximo de servidores com suporte é 12. Você pode ter até 20 servidores statefull definidos no fabric, dos quais 12 podem estar ativos e online a qualquer momento.