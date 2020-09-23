---
title: Adicionar Máquina de Front End
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: 69837016022f30453a287b6264936e20ec4883ca
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218312"
---
# <a name="add-front-end-machine"></a>Adicionar Máquina de Front End

Especifique o FQDN (nome de domínio totalmente qualificado) de cada computador que você deseja adicionar como Servidor Front-End a esse pool. Após adicionar um computador à lista, você poderá atualizar o FQDN do computador ou removê-lo do pool a qualquer momento antes da publicação da topologia. Depois da publicação da topologia, a alteração do FQDN exigirá a exclusão do servidor do Construtor de Topologia e a adição de um novo servidor ao pool com o novo FQDN. Para obter detalhes sobre a adição de um pool de Front-Ends à topologia, consulte [Define and Configure a Front End Pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx), na documentação de Implantação.

> [!IMPORTANT]
> Observe que o construtor de topologia indica que você pode ter até 20 servidores front-end em um pool. O número máximo de servidores com suporte é 12. Você pode ter até 20 servidores com monitoramento de estado definidos na malha, dos quais 12 podem estar ativos e online a qualquer momento.


