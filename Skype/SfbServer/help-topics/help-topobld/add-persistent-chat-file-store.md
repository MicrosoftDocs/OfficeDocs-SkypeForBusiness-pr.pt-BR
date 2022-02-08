---
title: Adicionar Arquivo de Chat Persistente do Repositório
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatFileStorePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: e1068706-ff61-4a98-8e51-4202111d936a
description: Você deve especificar um compartilhamento de arquivos a ser usado como o repositório de arquivos para o servidor Standard Edition ou o pool de Front-Ends Enterprise Edition. Você pode usar um compartilhamento de arquivos existente para o repositório de arquivos ou pode definir um novo especificando o FQDN (nome de domínio totalmente qualificado) do servidor de arquivos no qual o compartilhamento de arquivos deve estar localizado e um nome de pasta para o novo compartilhamento de arquivos.
ms.openlocfilehash: d049f84307d5bd9d2db0e833dbb44b85164e6cd6
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62391203"
---
# <a name="add-persistent-chat-file-store"></a>Adicionar Arquivo de Chat Persistente do Repositório
 
Você deve especificar um compartilhamento de arquivos a ser usado como o repositório de arquivos para o servidor Standard Edition ou o pool de Front-Ends Enterprise Edition. Você pode usar um compartilhamento de arquivos existente para o repositório de arquivos ou pode definir um novo especificando o FQDN (nome de domínio totalmente qualificado) do servidor de arquivos no qual o compartilhamento de arquivos deve estar localizado e um nome de pasta para o novo compartilhamento de arquivos.
  
> [!IMPORTANT]
> O compartilhamento de arquivos Skype for Business Server não pode ser localizado no servidor Edição Enterprise Front-End, mas pode estar localizado em um servidor Edição Standard. 
  
> [!IMPORTANT]
> Você pode definir o compartilhamento de arquivos no Construtor de Topologias antes de criar o repositório de arquivos, mas deve criar o repositório de arquivos no local definido por você antes de publicar a topologia. 
  
> [!IMPORTANT]
> Quando você adiciona um Servidor de Chat Persistente ou um pool de Servidores de Chat Persistente à sua topologia, o Construtor de Topologias deve ser capaz de configurar o armazenamento de arquivos e configurar listas de controle de acesso discricionário (DACLs) no compartilhamento de arquivos a ser usado para o armazenamento de arquivos. Isso exige que, quando executar o Construtor de Topologia para publicar a nova topologia, você esteja conectado com uma conta que tenha permissões de controle total (ler/escrever/modificar) para o compartilhamento de arquivos. 
  
## <a name="see-also"></a>Confira também

[Planejar o Servidor de Chat Persistente no Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Adicionar Servidor de Chat Persistente à topologia Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[Requisitos de hardware e software para o Servidor de Chat Persistente Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Requisitos de servidor para Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Noções básicas de topologia para Skype for Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md)
