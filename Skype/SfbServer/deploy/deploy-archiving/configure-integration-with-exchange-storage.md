---
title: Configurar a integração com o armazenamento do Exchange para o Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8f48b87f-a57f-4ed8-8c79-5c75b316b696
description: 'Resumo: Leia este tópico para saber como configurar a integração com o armazenamento do Exchange no Skype for Business Server.'
ms.openlocfilehash: b58aa090e4e6c51beb1f99ba5dc9020e029c8c39
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286422"
---
# <a name="configure-integration-with-exchange-storage-for-skype-for-business-server"></a>Configurar a integração com o armazenamento do Exchange para o Skype for Business Server
 
**Resumo:** Leia este tópico para saber como configurar a integração com o armazenamento do Exchange no Skype for Business Server.
  
Se você usa a integração do Microsoft Exchange para todos os usuários em sua implantação, não precisa configurar as políticas de arquivamento do Skype for Business Server para seus usuários. Em vez disso, configure as políticas de bloqueio do Exchange in loco para dar suporte ao arquivamento para usuários hospedados no Exchange, com as caixas de correio colocadas no bloqueio in-loco. Antes de configurar a integração com o armazenamento do Exchange, leia o [plano de arquivamento no Skype for Business Server](../../plan-your-deployment/archiving/archiving.md). Para obter detalhes sobre as políticas de bloqueio in-loco do Exchange, consulte a documentação do produto Exchange. 
  
## <a name="configure-integration-with-microsoft-exchange-storage"></a>Configurar a integração com o armazenamento do Microsoft Exchange

1. Usando uma conta de usuário atribuída à função CsArchivingAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2. Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server. 
    
3. Na barra de navegação da esquerda, clique em **Monitoramento e Arquivamento**, e depois, clique em **Configuração de Arquivamento**.
    
4. Clique no nome da configuração apropriada de pool, site ou global na lista de configurações de arquivamento, clique em **Editar**, **Mostrar detalhes** e faça o seguinte:
    
   - Para habilitar a integração com o armazenamento do Exchange, marque a caixa de seleção **integração do Microsoft Exchange** .
    
   - Para desabilitar a integração com o armazenamento do Exchange, desmarque a caixa de seleção **integração do Microsoft Exchange** .
    
5. Clique em **Confirmar**.
    
## <a name="when-skype-for-business-server-and-microsoft-exchange-are-deployed-in-different-forests"></a>Quando o Skype for Business Server e o Microsoft Exchange são implantados em florestas diferentes

Se você usa a integração do Microsoft Exchange e o Microsoft Exchange Server não está implantado na mesma floresta do Skype for Business Server, você deve verificar se os seguintes atributos do Exchange Active Directory estão sincronizados com a floresta em que o Skype for O Business Server é implantado:
  
- msExchUserHoldPolicies
    
- proxyAddresses
    
Este é um atributo com vários valores. Ao sincronizá-lo, você deve mesclar os valores, não substitui-los, de modo a garantir que os valores existentes não sejam perdidos.
  

