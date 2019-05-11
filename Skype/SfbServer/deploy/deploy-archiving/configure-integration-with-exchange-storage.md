---
title: Configurar a integração com o armazenamento do Exchange para Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8f48b87f-a57f-4ed8-8c79-5c75b316b696
description: 'Resumo: Leia este tópico para saber como configurar a integração com o armazenamento do Exchange no Skype para Business Server.'
ms.openlocfilehash: 4b9d689ef5315c58b2fb6d78c01366ce2377a00e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33893543"
---
# <a name="configure-integration-with-exchange-storage-for-skype-for-business-server"></a>Configurar a integração com o armazenamento do Exchange para Skype para Business Server
 
**Resumo:** Leia este tópico para saber como configurar a integração com o armazenamento do Exchange no Skype para Business Server.
  
Se você usar a integração do Microsoft Exchange para todos os usuários em sua implantação, você não precisará configurar Skype para políticas de arquivamento Business Server para seus usuários. Em vez disso, você pode configurar políticas de retenção de In-loco do Exchange para suportar o arquivamento para usuários hospedados no Exchange, com suas caixas de correio colocadas em retenção In-loco. Antes de configurar a integração com Exchange storage, leia [Planejar para arquivamento no Skype para Business Server](../../plan-your-deployment/archiving/archiving.md). Para obter detalhes sobre as políticas de retenção de In-loco do Exchange, consulte a documentação de produto do Exchange. 
  
## <a name="configure-integration-with-microsoft-exchange-storage"></a>Configurar a integração com o armazenamento do Microsoft Exchange

1. Usando uma conta de usuário atribuída à função CsArchivingAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. 
    
3. Na barra de navegação da esquerda, clique em **Monitoramento e Arquivamento**, e depois, clique em **Configuração de Arquivamento**.
    
4. Clique no nome da configuração apropriada de pool, site ou global na lista de configurações de arquivamento, clique em **Editar**, **Mostrar detalhes** e faça o seguinte:
    
   - Para habilitar a integração com o armazenamento do Exchange, marque a caixa de seleção **integração do Microsoft Exchange** .
    
   - Para desabilitar a integração com o armazenamento do Exchange, desmarque a caixa de seleção **integração do Microsoft Exchange** .
    
5. Clique em **Confirmar**.
    
## <a name="when-skype-for-business-server-and-microsoft-exchange-are-deployed-in-different-forests"></a>Quando o Skype para Business Server e Microsoft Exchange são implantados em florestas diferentes

Se você usar a integração do Microsoft Exchange e o Microsoft Exchange Server não estiver implantado na mesma floresta do Skype para Business Server, você deve garantir que os seguintes atributos do Active Directory do Exchange são sincronizados com a floresta onde Skype para Servidor de negócios é implantado:
  
- msExchUserHoldPolicies
    
- proxyAddresses
    
Este é um atributo com vários valores. Ao sincronizá-lo, você deve mesclar os valores, não substitui-los, de modo a garantir que os valores existentes não sejam perdidos.
  

