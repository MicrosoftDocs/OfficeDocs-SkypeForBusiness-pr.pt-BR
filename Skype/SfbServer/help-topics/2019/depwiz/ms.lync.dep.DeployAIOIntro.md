---
title: Preparar Servidor Standard Edition Único (Introdução)
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployAIOIntro
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fe11d380-54c9-47e7-a676-02b9a59dc93f
ROBOTS: NOINDEX, NOFOLLOW
description: Para iniciar a instalação de um Skype para servidor de Business Server Standard Edition que irá manter o repositório de gerenciamento Central e outros serviços colocados selecionado, você deve estar logado como membro do grupo Administradores local no servidor que se tornarão o servidor do Standard Edition. A página Preparar Servidor Standard Edition único detalha os requisitos para a instalação inicial. O computador precisa ser membro do domínio no qual você o implantará, e você precisa ter concluído com êxito a preparação do Esquema, Floresta e Domínio de sua floresta.
ms.openlocfilehash: b4b211899ba907a20d11f8adf4d2640599dc6f91
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32216582"
---
# <a name="prepare-single-standard-edition-server-intro"></a>Preparar Servidor Standard Edition Único (Introdução)
 
Para iniciar a instalação de um Skype para servidor de Business Server Standard Edition que irá manter o repositório de gerenciamento Central e outros serviços colocados selecionado, você deve estar logado como membro do grupo Administradores local no servidor que se tornarão o servidor do Standard Edition. A página **Preparar Servidor Standard Edition único** detalha os requisitos para a instalação inicial. O computador precisa ser membro do domínio no qual você o implantará, e você precisa ter concluído com êxito a preparação do Esquema, Floresta e Domínio de sua floresta.
  
Essa tarefa específica foi projetada para configurar um servidor Standard Edition como o primeiro servidor em sua infraestrutura. Esta tarefa instala o repositório de gerenciamento Central, que é o SQL Server Express, logon no servidor do Standard Edition. Se você já tiver outro servidor Standard Edition ou Pool de Front-Ends implantado, clique em **Cancelar**.
  
> [!NOTE]
> Depois de concluir esta tarefa, você instalará o construtor de topologia (se você não tiver instalado-lo) e configurar o documento de topologia. Não é possível publicar seu documento de topologia até exista um repositório de Gerenciamento Central disponível—que é implantado por meio da conclusão da tarefa descrita neste tópico. 
  

