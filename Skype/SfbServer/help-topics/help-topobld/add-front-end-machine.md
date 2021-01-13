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
ms.openlocfilehash: 4582aa09527dbc2e663dd6986772b5e88f980a0f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800141"
---
# <a name="add-front-end-machine"></a>Adicionar Máquina de Front-end

Especifique o FQDN (nome de domínio totalmente qualificado) de cada computador que você deseja adicionar como Servidor Front-End a esse pool. Após adicionar um computador à lista, você poderá atualizar o FQDN do computador ou removê-lo do pool a qualquer momento antes da publicação da topologia. Depois da publicação da topologia, a alteração do FQDN exigirá a exclusão do servidor do Construtor de Topologia e a adição de um novo servidor ao pool com o novo FQDN. Para obter detalhes sobre a adição de um pool de Front-Ends à topologia, consulte [Define and Configure a Front End Pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx), na documentação de Implantação.

> [!IMPORTANT]
> Observe que o Construtor de Topologias indica que você pode ter até 20 Servidores front-end em um pool. O número máximo de servidores com suporte é 12. Você pode ter até 20 servidores com estado definidos na malha, dos quais 12 podem estar ativos e online a qualquer momento.


