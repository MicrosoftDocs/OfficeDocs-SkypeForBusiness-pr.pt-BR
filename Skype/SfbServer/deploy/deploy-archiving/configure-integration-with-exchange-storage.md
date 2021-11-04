---
title: Configurar a integração com Exchange armazenamento para Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 8f48b87f-a57f-4ed8-8c79-5c75b316b696
description: 'Resumo: leia este tópico para saber como configurar a integração com Exchange armazenamento no Skype for Business Server.'
ms.openlocfilehash: 3ac2db718057b47ebe214c29e339b94dbc5e63a7
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60759183"
---
# <a name="configure-integration-with-exchange-storage-for-skype-for-business-server"></a>Configurar a integração com Exchange armazenamento para Skype for Business Server
 
**Resumo:** Leia este tópico para saber como configurar a integração com Exchange armazenamento no Skype for Business Server.
  
Se você usar a integração Exchange microsoft para todos os usuários em sua implantação, não precisará configurar Skype for Business Server de arquivamento para seus usuários. Em vez disso, você configura Exchange In-Place políticas de Espera para dar suporte ao arquivamento para usuários que estão Exchange, com suas caixas de correio colocadas em In-Place Hold. Antes de configurar a integração com Exchange armazenamento, leia [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md). Para obter detalhes sobre Exchange In-Place de espera, consulte a documentação Exchange do produto. 
  
## <a name="configure-integration-with-microsoft-exchange-storage"></a>Configurar a integração com o armazenamento Exchange Microsoft

1. A partir da conta do usuário que foi atribuída à função CsArchivingAdministrator ou CsAdministrator, faça o logon em qualquer computador na sua implantação interna.
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle. 
    
3. Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e clique em **Configuração do Arquivamento**.
    
4. Clique no nome da configuração do pool, local ou global adequada na lista de configurações de arquivamento, clique em **Editar**, em **Exibir detalhes** e faça o seguinte:
    
   - Para habilitar a integração com Exchange armazenamento, marque a caixa de seleção **integração Exchange Microsoft.**
    
   - Para desabilitar a integração com Exchange armazenamento, desem uma caixa de seleção de Exchange **integração da Microsoft.**
    
5. Clique em **Confirmar**.
    
## <a name="when-skype-for-business-server-and-microsoft-exchange-are-deployed-in-different-forests"></a>Quando Skype for Business Server e o Microsoft Exchange são implantados em florestas diferentes

Se você usar Exchange integração do Microsoft Microsoft Exchange Server e o Microsoft Exchange Server não for implantado na mesma floresta que o Skype for Business Server, certifique-se de que os seguintes atributos do Exchange Active Directory estejam sincronizados com a floresta onde o Skype for Business Server está implantado:
  
- msExchUserHoldPolicies
    
- proxyAddresses
    
Este é um atributo com vários valores. Ao sincronizá-lo, você deve mesclar os valores, não substitui-los, de modo a garantir que os valores existentes não sejam perdidos.
  

