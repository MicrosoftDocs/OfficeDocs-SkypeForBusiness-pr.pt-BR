---
title: Gerenciar bancos de dados com um Grupo de Disponibilidade AlwaysOn no Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: 'Resumo: saiba como adicionar mais bancos de dados Skype for Business Server a um Grupo de Disponibilidade AlwaysOn existente e saiba mais sobre as etapas adicionais necessárias após corrigir ou atualizar um Servidor Back-End que faz parte de um Grupo de Disponibilidade AlwaysOn no Skype for Business Server.'
ms.openlocfilehash: fe74cd804aff746a3d6c52163ed96d6b270703ce
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60827504"
---
# <a name="manage-databases-with-an-alwayson-availability-group-in-skype-for-business-server"></a>Gerenciar bancos de dados com um Grupo de Disponibilidade AlwaysOn no Skype for Business Server

Use as etapas deste artigo para adicionar mais bancos de dados Skype for Business Server a um Grupo de Disponibilidade AlwaysOn existente no Skype for Business Server e descubra sobre as etapas adicionais necessárias após corrigir ou atualizar um Servidor Back-End que faz parte de um Grupo de Disponibilidade AlwaysOn no Skype for Business Server.

## <a name="add-databases-to-an-alwayson-availability-group"></a>Adicionar bancos de dados a um Grupo de Disponibilidade AlwaysOn 

1. Abra SQL Server Management Studio e navegue até o Grupo de Disponibilidade AlwaysOn. Fail it over to the primary replica.
    
2. No Construtor de Topologias, de definir o SQL Server FQDN do Grupo de Disponibilidade AlwaysOn como o FQDN do nó principal desse grupo.
    
   - Abra o Construtor de Topologias, selecione **Baixar topologia da** implantação existente e clique em **OK**.
    
   - Expanda Skype for Business Server, expanda sua topologia e **expanda SQL Server Stores.** Clique com o botão direito do SQL do novo Grupo de Disponibilidade AlwaysOn e clique em **Editar Propriedades.**
    
   - Na parte inferior da página, na caixa **SQL Server FQDN,** digite o FQDN do nó principal do Grupo de Disponibilidade AlwaysOn.
    
3. Publique a topologia. No menu **Ação,** clique **em Topologia** e **publique**. Em seguida, na página de confirmação, clique **em Próximo**.
    
4. Use SQL Server Management Studio para adicionar o novo banco de dados ao Grupo de Disponibilidade AlwaysOn.
    
## <a name="patch-or-update-a-sql-server-in-an-alwayson-availability-group"></a>Corrigir ou atualizar um SQL Server em um Grupo de Disponibilidade AlwaysOn

Depois de corrigir um Servidor Back-End que faz parte de um Grupo de Disponibilidade AlwaysOn, você deve republicar a topologia.

1. Instale a atualização em seu servidor Skype for Business servidores ou servidores.
    
2. Execute o seguinte comando do PowerShell no Shell de Gerenciamento do Skype for Business (conectado com uma conta com permissão apropriada para aplicar alterações aos bancos de dados alwaysOn do SQL) da seguinte maneira:
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn [sqlpool.contoso.com] -Verbose
    ```

    Onde [sqlpool.contoso.com] é substituído pelo FQDN (nome de domínio totalmente qualificado) do seu grupo de disponibilidade AlwaysOn.
