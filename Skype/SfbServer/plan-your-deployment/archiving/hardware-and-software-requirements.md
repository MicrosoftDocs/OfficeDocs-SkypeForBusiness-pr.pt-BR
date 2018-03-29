---
title: Requisitos de hardware e software para arquivamento no Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 896d60e2-be4b-462d-8357-4cd307ab7304
description: 'Resumo: Leia este tópico para conhecer os requisitos de hardware e software para arquivamento no Skype para Business Server 2015.'
ms.openlocfilehash: d8d8039e95a3b578551d0db6ff219fe8f3c1e5c5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="hardware-and-software-requirements-for-archiving-in-skype-for-business-server-2015"></a>Requisitos de hardware e software para arquivamento no Skype for Business Server 2015
 
**Resumo:** Leia este tópico para conhecer os requisitos de hardware e software para arquivamento no Skype para Business Server 2015.
  
Skype para arquivamento Business Server 2015 agora é parte da função de Front-End, você não precisará instalar um servidor separado. No entanto, fazer, você precisa considerar os seguintes requisitos:
  
- Requisitos de infraestrutura
    
- Requisitos de software
    
- Requisitos de armazenamento de dados
    
## <a name="infrastructure-requirements"></a>Requisitos de infraestrutura

Skype para requisitos de infraestrutura de arquivamento de servidor de negócios são iguais às propriedades de implantação do Skype para Business Server. Para obter detalhes, consulte [Requirements for sua Skype para ambiente de negócios](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md). 
  
## <a name="prerequisite-software-requirements"></a>Requisitos de software

Pré-requisitos de arquivamento para Skype para Business Server são mais simples do que nas versões anteriores do Microsoft Lync Server devido a estes motivos: 
  
- Como o arquivamento não é mais é uma função de servidor, você não precisará instalar um servidor separado para arquivamento. Em vez disso, Agentes de Coleta de Dados Unificados são instalados e ativados automaticamente em todos os Pools de Front-Ends do Enterprise Edition e em todos os Servidores Standard Edition. Você precisa habilitar e publicar a topologia do seu arquivamento usando o Construtor de Topologias.
    
- Arquivamento usa o Skype para armazenamento de arquivos do servidor de negócios para armazenamento temporário de reunião arquivos de conteúdo, de modo que você não configurar um repositório de arquivos para arquivamento.
    
- No Skype para Business Server, Microsoft Message Queuing não é necessária.
    
## <a name="data-storage-requirements"></a>Requisitos de Armazenamento de Dados

Além disso, você deve configurar a infraestrutura para o armazenamento de arquivamento. Isso inclui selecionar uma ou ambas as opções abaixo:
  
- **Armazenamento do Microsoft Exchange**. Arquivos de conteúdo das reuniões, tais como apresentações em PowerPoint, são arquivados como anexo. Se você deseja armazenar Skype para dados de arquivo morto de negócios com os dados de conformidade do Exchange, você deve usar o Exchange para sua implantação do Exchange e certifique-se de que o tamanho máximo de armazenamento suporta o armazenamento dos arquivos de conteúdo de reunião. Você deve implantar o Exchange antes de implantar e habilitar o arquivamento usando a opção de integração do Microsoft Exchange. 
    
    Se você optar por usar o armazenamento do Exchange, você não precisará implantar bancos de dados do SQL Server separados para arquivamento, a menos que tenha Skype para usuários corporativos que não esteja hospedados em seus servidores Exchange. Se você implantar o arquivamento usando a opção de integração do Microsoft Exchange, Skype para dados de arquivo morto corporativos será armazenado com dados de conformidade do Exchange apenas para os usuários que estão hospedados em seus servidores Exchange. 
    
- **Skype para armazenamento de arquivamento Business Server**. Para suportar usuários que não esteja hospedados nos servidores do Exchange, ou se você não quiser usar a opção de integração do Microsoft Exchange, você deve implantar o armazenamento de arquivamento usando um banco de dados do SQL Server. Skype para Business Server suporta as seguintes versões de 64 bits do SQL Server:
    
  - Microsoft SQL Server 2008 R2 Enterprise
    
  - Microsoft SQL Server 2008 R2 Standard
    
  - Enterprise do Microsoft SQL Server 2012
    
  - Microsoft SQL Server 2012 Standard
    
  - Microsoft SQL Server 2014 Enterprise
    
  - Microsoft SQL Server 2014 Standard
    
    > [!NOTE]
    > Versões do Microsoft SQL Server Express não são suportadas para arquivamento. versões de 32 bits do SQL Server não são suportadas. Para requisitos do SQL Server e restrições adicionais, consulte [Requirements for sua Skype para ambiente de negócios](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md). 
  
    Você deve configurar as plataformas do SQL Server antes de implantar e habilitar o arquivamento. Se a conta utilizada para publicar a topologia tiver os direitos e permissões apropriados, é possível criar o banco de dados de arquivamento (LcsLog) ao publicar a topologia. Também é possível criar o banco de dados posteriormente, incluindo-o como parte do procedimento de instalação. Para obter detalhes sobre o SQL Server, consulte o [TechCenter do SQL Server](https://go.microsoft.com/fwlink/p/?linkID=129045).
    
    O aumento de carga para arquivamento pode ser significativo. Portanto, você deve assegurar que o espaço em disco é adequado para servidores Front-End no qual o arquivamento estiver habilitado.
    

