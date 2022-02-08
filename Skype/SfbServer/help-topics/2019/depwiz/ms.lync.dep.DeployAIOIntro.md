---
title: Preparar Servidor Standard Edition Único (Introdução)
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployAIOIntro
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: fe11d380-54c9-47e7-a676-02b9a59dc93f
ROBOTS: NOINDEX, NOFOLLOW
description: Para iniciar a instalação de um servidor Skype for Business Server Edição Standard que armazenará o armazenamento de Gerenciamento Central e outros serviços alocados selecionados, você deve estar conectado como membro do grupo administradores local no servidor que se tornará o servidor Edição Standard. A página Preparar Servidor Standard Edition único detalha os requisitos para a instalação inicial. O computador precisa ser membro do domínio no qual você o implantará, e você precisa ter concluído com êxito a preparação do Esquema, Floresta e Domínio de sua floresta.
ms.openlocfilehash: 09904d1c2ae13e88de90174d93d088836cb7101a
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62385189"
---
# <a name="prepare-single-standard-edition-server-intro"></a>Preparar Servidor Standard Edition Único (Introdução)
 
Para iniciar a instalação de um servidor Skype for Business Server Edição Standard que armazenará o armazenamento de Gerenciamento Central e outros serviços alocados selecionados, você deve estar conectado como membro do grupo administradores local no servidor que se tornará o servidor Edição Standard. A página **Preparar Servidor Standard Edition único** detalha os requisitos para a instalação inicial. O computador precisa ser membro do domínio no qual você o implantará, e você precisa ter concluído com êxito a preparação do Esquema, Floresta e Domínio de sua floresta.
  
Essa tarefa específica foi projetada para configurar um servidor Standard Edition como o primeiro servidor em sua infraestrutura. Essa tarefa instala o armazenamento de Gerenciamento Central, que é SQL Server Express, no servidor Edição Standard. Se você já tiver outro servidor Standard Edition ou pool de Front-Ends implantado, clique em **Cancelar**.
  
> [!NOTE]
> Depois de concluir essa tarefa, você instalará o Construtor de Topologias (se ainda não a instalou) e configurará seu documento de topologia. Não é possível publicar seu documento de topologia até exista um repositório de Gerenciamento Central disponível—que é implantado por meio da conclusão da tarefa descrita neste tópico. 
  

