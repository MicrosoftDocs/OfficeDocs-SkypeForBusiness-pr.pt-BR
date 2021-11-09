---
title: Preparar Esquema
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainSchemaPrep
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 337aa234-c5f3-4468-a047-2023848e942c
description: Para preparar o esquema para os Serviços de Domínio do Active Directory, execute a etapa Preparar Esquema no Assistente Skype for Business Server Implantação. Clique em Executar para começar a preparação do esquema. A etapa Preparar Esquema lê os arquivos de definição de esquema fornecidos no diretório /Program Files/Microsoft Lync Server 2013/Deployment/Setup no sistema no qual o Assistente de Implantação está sendo executado. Esses arquivos também estão disponíveis na mídia de instalação no diretório Suporte/Esquema. A etapa Preparar Esquema estenderá o esquema e informará o status do processo. Também o notificará quando o processo estiver concluído. A tela de resumo permitirá que você exiba os logs do processo. Revise os logs para ter certeza de que a preparação foi concluída e teve êxito.
ms.openlocfilehash: c4e1faa8a26fa74579d9c9177d2efbfda29fa40f
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60849044"
---
# <a name="prepare-schema"></a>Preparar Esquema
 
Para preparar o esquema para os Serviços de Domínio do Active Directory, execute a etapa Preparar Esquema no Assistente Skype for Business Server Implantação. Clique em **Executar** para começar a preparação do esquema. A etapa Preparar Esquema lê os arquivos de definição de esquema fornecidos no diretório \Program Files\Microsoft Lync Server 2013\Deployment\Setup no sistema no qual o Assistente de Implantação está sendo executado. Esses arquivos também estão disponíveis na mídia de instalação no diretório \Support\Schema. A etapa Preparar Esquema estenderá o esquema e informará o status do processo. Também o notificará quando o processo estiver concluído. A tela de resumo permitirá que você exiba os logs do processo. Revise os logs para ter certeza de que a preparação foi concluída e teve êxito.
  
> [!IMPORTANT]
> Para estender o esquema, é necessário estar conectado ao domínio como membro do grupo Admins. de Esquema e do grupo Administradores de Empresa. 
  
Classes e atributos são adicionados para estender o esquema de Serviços de Domínio do Active Directory para dar suporte Skype for Business Server de servidor, serviço e objetos de usuário de 2015. Antes de estender o esquema, é necessário realizar o backup do estado do Sistema do controlador de domínio que detém a função de mestre de esquema. Para obter detalhes sobre o processo de backup do Windows Server 2008 R2 com SP1, consulte [https://go.microsoft.com/fwlink/p/?linkId=207198](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee849849(v=ws.10)) . Para Windows Server 2003 e Windows Server 2003 R2, consulte [https://go.microsoft.com/fwlink/p/?linkId=207199](/previous-versions/windows/it-pro/windows-server-2003/cc787254(v=ws.10)) .
  
> [!CAUTION]
> A extensão do esquema não é reversível. Faça o máximo para limitar o possível impacto de uma extensão de esquema sem sucesso e para assegurar que a extensão do esquema terá êxito. Isso é fundamental no caso de uma perda de comunicação ou de qualquer outra falha no servidor. Você deve executar um backup do controlador de domínio mestre do esquema e um backup completo do Active Directory. 
  
Para executar um backup do controlador de domínio mestre do esquema e um backup completo do Active Directory:
  
1. Desconecte da rede o controlador de domínio que detém a função de mestre de esquema.
    
2. Execute um backup do Estado do Sistema do controlador de domínio que detém a função de mestre de esquema.
    
3. Estenda o esquema.
    
4. Após o êxito da extensão do esquema, reconecte o controlador de domínio à rede e saiba que a replicação está ativa e funcionando.
    
5. No caso improvável de uma falha de extensão de esquema, restaure o estado dos sistemas do controlador de domínio e do Active Directory usando o backup do Estado do Sistema que você fez anteriormente.
    
> [!NOTE]
> Se você precisar revisar os arquivos de log criados pelo Assistente de Implantação do Skype for Business Server, poderá encontrar os arquivos no computador onde o Assistente de Implantação foi executado, no diretório Usuários do usuário do Active Directory que executaram a etapa. Por exemplo, se o usuário fez logon como administrador de domínio no domínio Contoso.net, os arquivos de log estão localizados em: C:\Users\Administrator.Contoso\AppData\Local\Temp 
