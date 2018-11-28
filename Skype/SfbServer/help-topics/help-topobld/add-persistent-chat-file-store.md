---
title: Adicionar Repositório de Arquivo de Chat Persistente
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e1068706-ff61-4a98-8e51-4202111d936a
description: Você deve especificar um compartilhamento de arquivos a ser usado como o repositório de arquivos para o servidor Standard Edition ou o pool de Front-Ends Enterprise Edition. É possível usar um compartilhamento de arquivos existente para o repositório de arquivos ou definir um novo especificando o FQDN (nome de domínio totalmente qualificado) do servidor de arquivos no qual o compartilhamento de arquivos deve estar localizado e um nome de pasta para o novo compartilhamento de arquivos.
ms.openlocfilehash: 6463cb2c572be5d367e8788fc121ed0981bcb8a9
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2018
ms.locfileid: "19503820"
---
# <a name="add-persistent-chat-file-store"></a>Adicionar Repositório de Arquivo de Chat Persistente
 
Você deve especificar um compartilhamento de arquivos a ser usado como o repositório de arquivos para o servidor Standard Edition ou o pool de Front-Ends Enterprise Edition. É possível usar um compartilhamento de arquivos existente para o repositório de arquivos ou definir um novo especificando o FQDN (nome de domínio totalmente qualificado) do servidor de arquivos no qual o compartilhamento de arquivos deve estar localizado e um nome de pasta para o novo compartilhamento de arquivos.
  
> [!IMPORTANT]
> O compartilhamento de arquivo para Skype para Business Server não pode ser localizado no servidor Enterprise Edition Front End, mas pode estar localizado em um servidor Standard Edition. 
  
> [!IMPORTANT]
> Você pode definir o compartilhamento de arquivos no Construtor de Topologias antes de criar o repositório de arquivos, mas deve criar o repositório de arquivos no local definido por você antes de publicar a topologia. 
  
> [!IMPORTANT]
> Quando você adicionar um servidor de Chat persistente ou servidor de Chat persistente pool a sua topologia, construtor de topologia deve ser capaz de configurar o arquivo armazenar e configurar o controle de acesso discricionário DACLs (listas) no compartilhamento de arquivos a serem usados para o repositório de arquivos. Isso exige que, quando executar o Construtor de Topologias para publicar a nova topologia, você esteja conectado com uma conta que tenha permissões de controle total (ler/escrever/modificar) sobre o compartilhamento de arquivos. 
  
## <a name="see-also"></a>Consulte também

[Planejar Servidor de Chat Persistente no Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Adicionar servidor de Chat persistente à sua Skype para a topologia de negócios Server 2015](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[Requisitos de hardware e software para Servidor de Chat Persistente no Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Fundamentos de topologia para o Skype for Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md)