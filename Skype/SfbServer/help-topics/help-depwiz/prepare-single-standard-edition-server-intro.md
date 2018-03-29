---
title: Preparar Servidor Standard Edition Único (Introdução)
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/23/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployAIOIntro
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fe11d380-54c9-47e7-a676-02b9a59dc93f
description: Para iniciar a instalação de um Skype para servidor de Business Server 2015 Standard Edition que irá manter o repositório de gerenciamento Central e outros serviços colocados selecionado, você deve estar logado como membro do grupo Administradores local no servidor que irá Torne-se o servidor Standard Edition. Página preparar único Standard Edition Server fornece detalhes sobre os requisitos para a instalação inicial. O computador precisa ser membro do domínio no qual você o implantará, e você precisa ter concluído com êxito a preparação do Esquema, Floresta e Domínio de sua floresta.
ms.openlocfilehash: 9c43f3bc4574d35577b483cf1ca0748f78f3d04a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="prepare-single-standard-edition-server-intro"></a>Preparar Servidor Standard Edition Único (Introdução)
 
Para iniciar a instalação de um Skype para servidor de Business Server 2015 Standard Edition que irá manter o repositório de gerenciamento Central e outros serviços colocados selecionado, você deve estar logado como membro do grupo Administradores local no servidor que irá Torne-se o servidor Standard Edition. A página **Preparar Servidor Standard Edition único** detalha os requisitos para a instalação inicial. O computador precisa ser membro do domínio no qual você o implantará, e você precisa ter concluído com êxito a preparação do Esquema, Floresta e Domínio de sua floresta.
  
Essa tarefa específica foi projetada para configurar um servidor Standard Edition como o primeiro servidor em sua infraestrutura. Esta tarefa instala o repositório de gerenciamento Central, que é o SQL Server Express, logon no servidor do Standard Edition. Se você já tiver outro servidor Standard Edition ou Pool de Front-Ends implantado, clique em **Cancelar**.
  
> [!NOTE]
> Depois de concluir esta tarefa, você instalará o construtor de topologia (se você não tiver instalado-lo) e configurar o documento de topologia. Não é possível publicar seu documento de topologia até exista um repositório de Gerenciamento Central disponível—que é implantado por meio da conclusão da tarefa descrita neste tópico. 
  

