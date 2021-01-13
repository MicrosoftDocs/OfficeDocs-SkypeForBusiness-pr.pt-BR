---
title: Configurar a integração com o armazenamento do Exchange para o Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8f48b87f-a57f-4ed8-8c79-5c75b316b696
description: 'Resumo: Leia este tópico para saber como configurar a integração com o armazenamento do Exchange no Skype for Business Server.'
ms.openlocfilehash: 05a0c65aaca54e469f30dd5e732565f6ec0bbb4b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825061"
---
# <a name="configure-integration-with-exchange-storage-for-skype-for-business-server"></a>Configurar a integração com o armazenamento do Exchange para o Skype for Business Server
 
**Resumo:** Leia este tópico para saber como configurar a integração com o armazenamento do Exchange no Skype for Business Server.
  
Se você usar a integração com o Microsoft Exchange para todos os usuários em sua implantação, não precisará configurar as políticas de arquivamento do Skype for Business Server para seus usuários. Em vez disso, você configura as In-Place de Espera do Exchange para dar suporte ao arquivamento para usuários que estão no Exchange, com suas caixas de correio colocadas em In-Place Espera. Antes de configurar a integração com o armazenamento do Exchange, leia [Planejar o arquivamento no Skype for Business Server.](../../plan-your-deployment/archiving/archiving.md) Para obter detalhes sobre as In-Place De espera do Exchange, consulte a documentação do produto do Exchange. 
  
## <a name="configure-integration-with-microsoft-exchange-storage"></a>Configurar a integração com o armazenamento do Microsoft Exchange

1. A partir da conta do usuário que foi atribuída à função CsArchivingAdministrator ou CsAdministrator, faça o logon em qualquer computador na sua implantação interna.
    
2. Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server. 
    
3. Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e clique em **Configuração do Arquivamento**.
    
4. Clique no nome da configuração do pool, local ou global adequada na lista de configurações de arquivamento, clique em **Editar**, em **Exibir detalhes** e faça o seguinte:
    
   - Para habilitar a integração com o armazenamento do Exchange, marque a caixa de seleção de integração do **Microsoft Exchange.**
    
   - Para desabilitar a integração com o armazenamento do Exchange, des limpe a caixa de seleção de integração do **Microsoft Exchange.**
    
5. Clique em **Confirmar**.
    
## <a name="when-skype-for-business-server-and-microsoft-exchange-are-deployed-in-different-forests"></a>Quando o Skype for Business Server e o Microsoft Exchange são implantados em florestas diferentes

Se você usar a integração com o Microsoft Exchange e o Microsoft Exchange Server não for implantado na mesma floresta que o Skype for Business Server, deverá garantir que os seguintes atributos do Exchange Active Directory estejam sincronizados com a floresta onde o Skype for Business Server está implantado:
  
- msExchUserHoldPolicies
    
- proxyAddresses
    
Este é um atributo com vários valores. Ao sincronizá-lo, você deve mesclar os valores, não substitui-los, de modo a garantir que os valores existentes não sejam perdidos.
  

