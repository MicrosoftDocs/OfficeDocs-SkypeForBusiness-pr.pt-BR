---
title: Preparar Servidor Standard Edition Único (Introdução)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployAIOIntro
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: fe11d380-54c9-47e7-a676-02b9a59dc93f
ROBOTS: NOINDEX, NOFOLLOW
description: Para começar a instalação de um servidor do Skype for Business Server Standard Edition que conterá o repositório de gerenciamento central e outros serviços posicionados que você selecionar, você deve estar conectado como um membro do grupo Administradores local no servidor que se tornará o servidor Standard Edition. A página Preparar Servidor Standard Edition único detalha os requisitos para a instalação inicial. O computador precisa ser membro do domínio no qual você o implantará, e você precisa ter concluído com êxito a preparação do Esquema, Floresta e Domínio de sua floresta.
ms.openlocfilehash: 437f90fa99efa920479e7c0dc966c3c63fd5eed1
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41796972"
---
# <a name="prepare-single-standard-edition-server-intro"></a>Preparar Servidor Standard Edition Único (Introdução)
 
Para começar a instalação de um servidor do Skype for Business Server Standard Edition que conterá o repositório de gerenciamento central e outros serviços posicionados que você selecionar, você deve estar conectado como um membro do grupo Administradores local no servidor que se tornará o servidor Standard Edition. A página **Preparar Servidor Standard Edition único** detalha os requisitos para a instalação inicial. O computador precisa ser membro do domínio no qual você o implantará, e você precisa ter concluído com êxito a preparação do Esquema, Floresta e Domínio de sua floresta.
  
Essa tarefa específica foi projetada para configurar um servidor Standard Edition como o primeiro servidor em sua infraestrutura. Esta tarefa instala o repositório de gerenciamento central, que é o SQL Server Express, no servidor Standard Edition. Se você já tiver outro servidor Standard Edition ou Pool de Front-Ends implantado, clique em **Cancelar**.
  
> [!NOTE]
> Depois de concluir essa tarefa, você instalará o construtor de topologias (caso ainda não o tenha instalado) e configurará o documento de topologia. Não é possível publicar seu documento de topologia até exista um repositório de Gerenciamento Central disponível—que é implantado por meio da conclusão da tarefa descrita neste tópico. 
  

