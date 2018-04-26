---
title: Configurar integração com o armazenamento do Exchange no Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8f48b87f-a57f-4ed8-8c79-5c75b316b696
description: 'Resumo: leia este tópico para aprender como configurar a integração com o armazenamento do Exchange no .'
ms.openlocfilehash: 2d814bb297999062aaf93160286031afec51c3a9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-integration-with-exchange-storage-for-skype-for-business-server-2015"></a>Configurar integração com o armazenamento do Exchange no Skype for Business Server 2015
 
Resumo: leia este tópico para aprender como configurar a integração com o armazenamento do Exchange no .
  
Se você usar a integração com o  para todos os usuários da implantação, não será necessário configurar as políticas de arquivamento do  para todos os usuários. Em vez disso, configure as políticas de retenção no local do  a fim de oferecer suporte ao arquivamento para usuários hospedados no , com suas caixas de correio em retenção no local. Before you configure integration with Exchange storage, read [Plan for archiving in Skype for Business Server 2015](../../plan-your-deployment/archiving/archiving.md). Para obter detalhes sobre políticas de Bloqueio In-loco do Exchange, consulte a documentação do produto . 
  
## <a name="configure-integration-with-microsoft-exchange-storage"></a>Configurar integração com o armazenamento do Exchange

1. Usando uma conta de usuário atribuída à função CsArchivingAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2. Você também pode abrir uma janela do navegador e inserir a URL do Administrador para abrir o Painel de Controle do Skype for Business Server. 
    
3. Na barra de navegação da esquerda, clique em **Monitoramento e Arquivamento**, e depois, clique em **Configuração de Arquivamento**.
    
4. Clique no nome da configuração apropriada de pool, site ou global na lista de configurações de arquivamento, clique em **Editar**, **Mostrar detalhes** e faça o seguinte:
    
  - Para habilitar a integração com o armazenamento do , marque a caixa de seleção .
    
  - Para desabilitar a integração com o armazenamento do , desmarque a caixa de seleção .
    
5. Clique em **Confirmar**.
    
## <a name="when-skype-for-business-server-and-microsoft-exchange-are-deployed-in-different-forests"></a>When Skype for Business Server and Microsoft Exchange are deployed in different forests

Se você usar a integração com o  e o  não estiver implantado na mesma floresta que o , você deverá verificar se os seguintes atributos do Active Directory do  estão sincronizados com a floresta onde o  está implantado:
  
- msExchUserHoldPolicies
    
- proxyAddresses
    
Este é um atributo com vários valores. Ao sincronizá-lo, você deve mesclar os valores, não substitui-los, de modo a garantir que os valores existentes não sejam perdidos.
  

