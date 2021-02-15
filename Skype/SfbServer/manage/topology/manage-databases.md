---
title: Gerenciar bancos de dados com um Grupo de Disponibilidade AlwaysOn no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: 'Resumo: saiba como adicionar mais bancos de dados do Skype for Business Server a um Grupo de Disponibilidade AlwaysOn existente e saiba mais sobre as etapas adicionais necessárias após corrigir ou atualizar um Servidor Back End que faz parte de um Grupo de Disponibilidade AlwaysOn no Skype for Business Server.'
ms.openlocfilehash: 444194c9cda5f4c3f82e6f3f7698395dce1a5d07
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826361"
---
# <a name="manage-databases-with-an-alwayson-availability-group-in-skype-for-business-server"></a>Gerenciar bancos de dados com um Grupo de Disponibilidade AlwaysOn no Skype for Business Server

Use as etapas deste artigo para adicionar mais bancos de dados do Skype for Business Server a um Grupo de Disponibilidade AlwaysOn existente no Skype for Business Server e saiba mais sobre as etapas adicionais necessárias depois de corrigir ou atualizar um Servidor Back End que faz parte de um Grupo de Disponibilidade AlwaysOn no Skype for Business Server.

## <a name="add-databases-to-an-alwayson-availability-group"></a>Adicionar bancos de dados a um Grupo de Disponibilidade AlwaysOn 

1. Abra o SQL Server Management Studio e navegue até o Grupo de Disponibilidade AlwaysOn. Fail over it over to the primary replica.
    
2. No Construtor de Topologias, de definir o FQDN do SQL Server do Grupo de Disponibilidade AlwaysOn como o FQDN do nó principal desse grupo.
    
   - Abra o Construtor de Topologias, **selecione Baixar topologia da implantação existente** e clique em **OK.**
    
   - Expanda o Skype for Business Server, expanda sua topologia e expanda os **Armazenamentos do SQL Server.** Clique com o botão direito do mouse no armazenamento SQL do novo Grupo de Disponibilidade AlwaysOn e clique em **Editar Propriedades.**
    
   - Na parte inferior da página, na caixa **FQDN** do SQL Server, digite o FQDN do nó principal do Grupo de Disponibilidade AlwaysOn.
    
3. Publique a topologia. No menu **Ação,** clique **em Topologia** e **publique.** Em seguida, na página de confirmação, clique em **Próximo**.
    
4. Use o SQL Server Management Studio para adicionar o novo banco de dados ao Grupo de Disponibilidade AlwaysOn.
    
## <a name="patch-or-update-a-sql-server-in-an-alwayson-availability-group"></a>Corrigir ou atualizar um SQL Server em um grupo de disponibilidade AlwaysOn

Depois de corrigir um Servidor Back End que faz parte de um Grupo de Disponibilidade AlwaysOn, você deve republicar a topologia.

1. Instale a atualização no servidor ou servidores do Skype for Business.
    
2. Execute o seguinte comando do PowerShell no Shell de Gerenciamento do Skype for Business (conectado com uma conta corretamente com permissão para aplicar alterações aos bancos de dados SQL AlwaysOn) da seguinte maneira:
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn [sqlpool.contoso.com] -Verbose
    ```

    Onde [sqlpool.contoso.com] é substituído pelo nome de domínio totalmente qualificado (FQDN) do seu grupo de disponibilidade AlwaysOn.
