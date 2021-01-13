---
title: Adicionar Arquivo de Chat Persistente do Repositório
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e1068706-ff61-4a98-8e51-4202111d936a
description: Você deve especificar um compartilhamento de arquivos a ser usado como o repositório de arquivos para o servidor Standard Edition ou o pool de Front-Ends Enterprise Edition. Você pode usar um compartilhamento de arquivos existente para o repositório de arquivos ou pode definir um novo especificando o FQDN (nome de domínio totalmente qualificado) do servidor de arquivos no qual o compartilhamento de arquivos deve estar localizado e um nome de pasta para o novo compartilhamento de arquivos.
ms.openlocfilehash: c77087520e51fffcad8c8341fe33103327e17799
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818671"
---
# <a name="add-persistent-chat-file-store"></a>Adicionar Arquivo de Chat Persistente do Repositório
 
Você deve especificar um compartilhamento de arquivos a ser usado como o repositório de arquivos para o servidor Standard Edition ou o pool de Front-Ends Enterprise Edition. Você pode usar um compartilhamento de arquivos existente para o repositório de arquivos ou pode definir um novo especificando o FQDN (nome de domínio totalmente qualificado) do servidor de arquivos no qual o compartilhamento de arquivos deve estar localizado e um nome de pasta para o novo compartilhamento de arquivos.
  
> [!IMPORTANT]
> O compartilhamento de arquivos do Skype for Business Server não pode estar localizado no Servidor de Front End Enterprise Edition, mas pode estar localizado em um servidor Standard Edition. 
  
> [!IMPORTANT]
> Você pode definir o compartilhamento de arquivos no Construtor de Topologias antes de criar o repositório de arquivos, mas deve criar o repositório de arquivos no local definido por você antes de publicar a topologia. 
  
> [!IMPORTANT]
> Quando você adiciona um Servidor de Chat Persistente ou pool de Servidor de Chat Persistente à sua topologia, o Construtor de Topologias deve ser capaz de configurar o armazenamento de arquivos e configurar as listas de controle de acesso discricionário (DACLs) no compartilhamento de arquivos a ser usado para o armazenamento de arquivos. Isso exige que, quando executar o Construtor de Topologia para publicar a nova topologia, você esteja conectado com uma conta que tenha permissões de controle total (ler/escrever/modificar) para o compartilhamento de arquivos. 
  
## <a name="see-also"></a>Confira também

[Plano para Servidor de Chat Persistente no Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Adicionar Servidor de Chat Persistente à sua topologia do Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[Requisitos de hardware e software para o Servidor de Chat Persistente no Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Requisitos de servidor para o Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Noções básicas de topologia do Skype for Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md)
