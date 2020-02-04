---
title: Preparar Servidor Standard Edition Único (Introdução)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployAIOIntro
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fe11d380-54c9-47e7-a676-02b9a59dc93f
description: Para começar a instalação de um servidor do Skype for Business Server 2015 Standard Edition que conterá o repositório de gerenciamento central e outros serviços posicionados que você selecionar, você deve estar conectado como um membro do grupo Administradores local no servidor que irá Torne-se o servidor Standard Edition. A página Preparar Servidor Standard Edition único detalha os requisitos para a instalação inicial. O computador precisa ser membro do domínio no qual você o implantará, e você precisa ter concluído com êxito a preparação do Esquema, Floresta e Domínio de sua floresta.
ms.openlocfilehash: ed7c353f602d97842e654faa5b539a6dcae01133
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41687344"
---
# <a name="prepare-single-standard-edition-server-intro"></a>Preparar Servidor Standard Edition Único (Introdução)
 
Para começar a instalação de um servidor do Skype for Business Server 2015 Standard Edition que conterá o repositório de gerenciamento central e outros serviços posicionados que você selecionar, você deve estar conectado como um membro do grupo Administradores local no servidor que irá Torne-se o servidor Standard Edition. A página **Preparar Servidor Standard Edition único** detalha os requisitos para a instalação inicial. O computador precisa ser membro do domínio no qual você o implantará, e você precisa ter concluído com êxito a preparação do Esquema, Floresta e Domínio de sua floresta.
  
Essa tarefa específica foi projetada para configurar um servidor Standard Edition como o primeiro servidor em sua infraestrutura. Esta tarefa instala o repositório de gerenciamento central, que é o SQL Server Express, no servidor Standard Edition. Se você já tiver outro servidor Standard Edition ou Pool de Front-Ends implantado, clique em **Cancelar**.
  
> [!NOTE]
> Depois de concluir essa tarefa, você instalará o construtor de topologias (caso ainda não o tenha instalado) e configurará o documento de topologia. Não é possível publicar seu documento de topologia até exista um repositório de Gerenciamento Central disponível—que é implantado por meio da conclusão da tarefa descrita neste tópico. 
  

