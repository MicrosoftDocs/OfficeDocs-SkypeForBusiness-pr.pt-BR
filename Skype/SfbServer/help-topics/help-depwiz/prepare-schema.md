---
title: Preparar Esquema
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainSchemaPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 337aa234-c5f3-4468-a047-2023848e942c
description: Para preparar o esquema para os serviços de domínio Active Directory, execute a etapa preparar esquema no assistente de implantação do Skype for Business Server. Clique em Executar para iniciar a preparação do esquema. A etapa preparar esquema lê os arquivos de definição de esquema fornecidos no diretório arquivos/Program/Microsoft Lync Server 2013/Deployment/setup no sistema em que o assistente de implantação está em execução. Esses arquivos também estão disponíveis na mídia de instalação no diretório de suporte/esquema. A etapa Preparar Esquema estenderá o esquema e informará o status do processo. Você também será notificado quando o processo for concluído. A tela de resumo permitirá que você exiba os logs do processo. Revise os logs para ter certeza de que a preparação foi concluída e teve êxito.
ms.openlocfilehash: 12b4bcbe93bd1ed55e0a2c2c1a133db41b30cd00
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34292120"
---
# <a name="prepare-schema"></a>Preparar Esquema
 
Para preparar o esquema para os serviços de domínio Active Directory, execute a etapa preparar esquema no assistente de implantação do Skype for Business Server. Clique em **Executar** para iniciar a preparação do esquema. A etapa Preparar Esquema lê os arquivos de definição de esquema fornecidos no diretório \Program Files\Microsoft Lync Server 2013\Deployment\Setup no sistema no qual o Assistente de Implantação está sendo executado. Esses arquivos também estão disponíveis na mídia de instalação no diretório \Support\Schema. A etapa Preparar Esquema estenderá o esquema e informará o status do processo. Você também será notificado quando o processo for concluído. A tela de resumo permitirá que você exiba os logs do processo. Revise os logs para ter certeza de que a preparação foi concluída e teve êxito.
  
> [!IMPORTANT]
> Para estender o esquema, é necessário estar conectado ao domínio como membro do grupo Administradores de Esquema e do grupo Administradores de Empresa. 
  
Classes e atributos são adicionados para estender o esquema de serviços de domínio Active Directory para dar suporte a objetos de servidor, serviço e usuário do Skype for Business Server 2015. Antes de estender o esquema, é necessário fazer o backup do Estado do Sistema do controlador de domínio que detém a função de mestre de esquema. Para obter detalhes sobre o processo de backup do Windows Server 2008 R2 com SP1 [https://go.microsoft.com/fwlink/p/?linkId=207198](https://go.microsoft.com/fwlink/p/?linkId=207198), consulte. Para o Windows Server 2003 e o Windows Server 2003 R2 [https://go.microsoft.com/fwlink/p/?linkId=207199](https://go.microsoft.com/fwlink/p/?linkId=207199), consulte.
  
> [!CAUTION]
> A extensão do esquema não é reversível. Faça o máximo para limitar o possível impacto de uma extensão de esquema sem sucesso e para assegurar que a extensão do esquema terá êxito. Isso é fundamental no caso de uma perda de comunicação ou de qualquer outra falha no servidor. Você deve executar um backup do controlador de domínio do mestre de esquema e um backup completo do Active Directory. 
  
Para executar um backup do controlador de domínio do mestre de esquema e um backup completo do Active Directory:
  
1. Desconecte da rede o controlador de domínio que detém a função de mestre de esquema.
    
2. Execute um backup do Estado do Sistema do controlador de domínio que detém a função de mestre de esquema.
    
3. Estenda o esquema.
    
4. Após o êxito da extensão do esquema, reconecte o controlador de domínio à rede e saiba que a replicação está ativa e funcionando.
    
5. No evento improvável de uma falha na extensão do esquema, restaure o estado do sistema do controlador de domínio e do Active Directory usando o backup do estado do sistema que você tirou anteriormente.
    
> [!NOTE]
> Se precisar examinar os arquivos de log criados pelo assistente de implantação do Skype for Business Server, você poderá localizar os arquivos no computador em que o assistente de implantação foi executado, no diretório usuários do usuário do Active Directory que executou a etapa. Por exemplo, se o usuário tiver entrado como administrador do domínio no domínio Contoso.net, os arquivos de log serão localizados em: C:\Users\Administrator.Contoso\AppData\Local\Temp 
  

