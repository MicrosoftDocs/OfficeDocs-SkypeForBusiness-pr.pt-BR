---
title: Preparar Esquema
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainSchemaPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 337aa234-c5f3-4468-a047-2023848e942c
description: Para preparar o esquema do Active Directory Domain Services, você executar a etapa de preparação de esquema no Skype para o Assistente de implantação de servidor de negócios. Clique em Executar para iniciar a preparação do esquema. A etapa de preparar esquema lê os arquivos de definição de esquema fornecido no diretório/programa arquivos/Microsoft Lync Server 2013/implantação/instalação no sistema que está executando o Assistente para implantação. Esses arquivos também estão disponíveis na mídia de instalação no diretório suporte/esquema. A etapa Preparar Esquema estenderá o esquema e informará o status do processo. Você também será notificado quando o processo for concluído. A tela de resumo permitirá que você exiba os logs do processo. Revise os logs para ter certeza de que a preparação foi concluída e teve êxito.
ms.openlocfilehash: 8565a3474b309820714949b5aa6f4544c72a23bd
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30891005"
---
# <a name="prepare-schema"></a>Preparar Esquema
 
Para preparar o esquema do Active Directory Domain Services, você executar a etapa de preparação de esquema no Skype para o Assistente de implantação de servidor de negócios. Clique em **Executar** para iniciar a preparação do esquema. A etapa Preparar Esquema lê os arquivos de definição de esquema fornecidos no diretório \Program Files\Microsoft Lync Server 2013\Deployment\Setup no sistema no qual o Assistente de Implantação está sendo executado. Esses arquivos também estão disponíveis na mídia de instalação no diretório \Support\Schema. A etapa Preparar Esquema estenderá o esquema e informará o status do processo. Você também será notificado quando o processo for concluído. A tela de resumo permitirá que você exiba os logs do processo. Revise os logs para ter certeza de que a preparação foi concluída e teve êxito.
  
> [!IMPORTANT]
> Para estender o esquema, é necessário estar conectado ao domínio como membro do grupo Administradores de Esquema e do grupo Administradores de Empresa. 
  
Classes e atributos são adicionados para estender o esquema do Active Directory Domain Services para suportar Skype para servidor Business Server 2015, serviço e objetos de usuário. Antes de estender o esquema, é necessário fazer o backup do Estado do Sistema do controlador de domínio que detém a função de mestre de esquema. Para obter detalhes sobre o processo de backup do Windows Server 2008 R2 com SP1, consulte [https://go.microsoft.com/fwlink/p/?linkId=207198](https://go.microsoft.com/fwlink/p/?linkId=207198). Para Windows Server 2003 e Windows Server 2003 R2, consulte [https://go.microsoft.com/fwlink/p/?linkId=207199](https://go.microsoft.com/fwlink/p/?linkId=207199).
  
> [!CAUTION]
> A extensão do esquema não é reversível. Faça o máximo para limitar o possível impacto de uma extensão de esquema sem sucesso e para assegurar que a extensão do esquema terá êxito. Isso é fundamental no caso de uma perda de comunicação ou de qualquer outra falha no servidor. Você deve executar um backup do controlador de domínio mestre de esquema e um backup completo do Active Directory. 
  
Para realizar um backup do controlador de domínio mestre de esquema e um backup completo do Active Directory:
  
1. Desconecte da rede o controlador de domínio que detém a função de mestre de esquema.
    
2. Execute um backup do Estado do Sistema do controlador de domínio que detém a função de mestre de esquema.
    
3. Estenda o esquema.
    
4. Após o êxito da extensão do esquema, reconecte o controlador de domínio à rede e saiba que a replicação está ativa e funcionando.
    
5. Na hipótese remota de uma expansão fracassada de esquema, restaure o estado do sistema do controlador de domínio e do Active Directory usando o backup do estado do sistema realizado anteriormente.
    
> [!NOTE]
> Se você precisar revisar os arquivos de log são criados pelo Skype para o Assistente de implantação de servidor de negócios, você pode encontrar os arquivos no computador onde o Assistente de implantação foi executado, no diretório de usuários do usuário do Active Directory que executou a etapa. Por exemplo, se o usuário logado como administrador de domínio no domínio Contoso.net, os arquivos de log estão localizados em: C:\Users\Administrator.Contoso\AppData\Local\Temp 
  

