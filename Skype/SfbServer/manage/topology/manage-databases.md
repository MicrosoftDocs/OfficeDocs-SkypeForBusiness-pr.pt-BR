---
title: Gerenciar bancos de dados com um grupo de disponibilidade do AlwaysOn no Skype para Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: 'Resumo: Saiba como adicionar mais Skype para bancos de dados do Business Server a um grupo de disponibilidade do AlwaysOn existente e saiba mais sobre as etapas adicionais necessárias após você patch ou atualização de um servidor Back-End que faz parte de um grupo de disponibilidade do AlwaysOn em Skype para Servidor de negócios.'
ms.openlocfilehash: ca7a792e001c29e087b9b6ac1637029c90ea1ae9
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222804"
---
# <a name="manage-databases-with-an-alwayson-availability-group-in-skype-for-business-server"></a>Gerenciar bancos de dados com um grupo de disponibilidade do AlwaysOn no Skype para Business Server

Use as etapas neste artigo para adicionar mais Skype para bancos de dados do Business Server a um grupo de disponibilidade do AlwaysOn existente no Skype para Business Server e saiba mais sobre as etapas adicionais necessárias depois de patch ou atualização de um servidor Back-End que faz parte de um AlwaysOn Grupo de disponibilidade no Skype para Business Server.

## <a name="add-databases-to-an-alwayson-availability-group"></a>Adicionar bancos de dados para um grupo de disponibilidade do AlwaysOn 

1. Abra o SQL Server Management Studio e navegue até o grupo de disponibilidade do AlwaysOn. Failover para a réplica primária.
    
2. No construtor de topologia, defina o FQDN do grupo de disponibilidade do AlwaysOn do SQL Server para o FQDN do nó principal desse grupo.
    
   - Abra o construtor de topologia, selecione **Baixar topologia da implantação existente**e clique em **Okey**.
    
   - Expanda o Skype for Business Server, expanda sua topologia e expanda **Repositórios do SQL Server**. Clique com o botão o repositório SQL do novo grupo de disponibilidade do AlwaysOn e clique em **Editar propriedades**.
    
   - Na parte inferior da página, na caixa **FQDN do SQL Server** , digite o FQDN do nó principal do grupo de disponibilidade do AlwaysOn.
    
3. Publique a topologia. No menu **Ação**, clique em **Topologia** e, em seguida, **Publicar**. Na página de confirmação, clique em **Avançar**.
    
4. Use o SQL Server Management Studio para adicionar o novo banco de dados para o grupo de disponibilidade do AlwaysOn.
    
## <a name="patch-or-update-a-sql-server-in-an-alwayson-availability-group"></a>Aplicar patch ou atualizar o SQL Server em um grupo de disponibilidade AlwaysOn

Depois de aplicar o patch de um servidor Back-End que faz parte de um grupo de disponibilidade do AlwaysOn, você deve republicar a topologia.

1. Instale a atualização em um ou vários servidores do Skype for Business.
    
2. Execute o seguinte comando do PowerShell no Skype for Business Management Shell (acessado com uma conta que tenha a devida permissão para aplicar alterações nos bancos de dados do SQL AlwaysOn) conforme segue:
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn [sqlpool.contoso.com] -Verbose
    ```

    Quando o [sqlpool.contoso.com] é substituído pelo FQDN (Nome do domínio totalmente qualificado) do seu grupo de disponibilidade AlwaysOn.