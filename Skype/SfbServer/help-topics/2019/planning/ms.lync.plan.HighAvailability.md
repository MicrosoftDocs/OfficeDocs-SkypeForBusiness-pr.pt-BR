---
title: Alta disponibilidade (ferramenta de planejamento)
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.plan.HighAvailability
- ms.lync.plan.HighAvailability
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14a897b3-2406-46c7-b08f-490085b3d048
description: O esquema principal de alta disponibilidade para a maioria das funções de servidor em Skype para Business Server se baseia em redundância de servidor por meio do pool. Se um servidor que executa determinada função de servidor falhar, os outros servidores que executam a mesma função no pool assumirão a carga daquele servidor.
ms.openlocfilehash: 140f413644360e8c776c48dbde5979cb4b57b04a
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20990118"
---
# <a name="high-availability-planning-tool"></a>Alta disponibilidade (ferramenta de planejamento)
 
O esquema principal de alta disponibilidade para a maioria das funções de servidor em Skype para Business Server se baseia em redundância de servidor por meio do pool. Se um servidor que executa determinada função de servidor falhar, os outros servidores que executam a mesma função no pool assumirão a carga daquele servidor.
  
Skype para Business Server requer pelo menos dois servidores Front-End para habilitar a alta disponibilidade. A ferramenta de planejamento usa os seguintes critérios para determinar se ele adicionará servidores adicionais para dar suporte à alta disponibilidade:
  
- Se a implantação contiver dois ou mais servidores Front-End, a ferramenta de planejamento não adiciona um servidor adicional.
    
- Se a implantação contiver um servidor de borda, um servidor adicional é adicionado. 
    
- Se a implantação contiver Chat persistente, a ferramenta de planejamento irá adicionar um servidor extra, mas não aumentar o número de pool. Por exemplo, se a implantação já contiver quatro servidores, a ferramenta de planejamento irá sugerir adicionando um servidor adicional (para um total de cinco servidores) mas manterá um único pool. 

    > [!NOTE] 
    > Bate-papo persistente está disponível no Skype para Business Server 2015, mas não é mais suportado no Skype para Business Server 2019. A mesma funcionalidade está disponível em equipes. Para obter mais informações, consulte [Atualizar Skype para negócios às equipes da Microsoft](https://docs.microsoft.com/MicrosoftTeams/journey-skypeforbusiness-teams). Se você precisar utilizar o chat persistente, suas opções são migrar usuários exigir que essa funcionalidade para equipes ou continuar usando Skype para Business Server 2015. 

    
A ferramenta de planejamento também adiciona um banco de dados do SQL de espelho para todos os bancos de dados. Por exemplo, se houver um banco de dados do servidor SQL Front-End, a ferramenta de planejamento irá adicionar outro banco de dados como o banco de dados de espelho para que este e nomeie-o como o "banco de dados SQL de espelho de Front-End.
  
Para obter mais detalhes sobre como preparar seu ambiente para alta disponibilidade, consulte [Planejar a alta disponibilidade e recuperação de desastres em Skype para Business Server](../../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  

