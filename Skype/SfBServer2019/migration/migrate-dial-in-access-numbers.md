---
title: Migrar números de acesso de discagem
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Migrar números de acesso de discagem para o Skype for Business Server 2019 requer a execução do cmdlet Move-CsApplicationEndpoint para migrar os objetos de contato. Durante a instalação herdada e o período de coexistência do Skype for Business Server 2019, os números de acesso discado que você criou no Skype for Business Server 2019 se comportam de forma semelhante aos números de acesso de discagem que você cria na instalação herdada, conforme descrito neste seção.
ms.openlocfilehash: 5333cc7cb835fc6bf324de9ab12a868f95b72972
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813499"
---
# <a name="migrate-dial-in-access-numbers"></a>Migrar números de acesso de discagem

Migrar números de acesso de discagem para o Skype for Business Server 2019 requer a execução do cmdlet **move-CsApplicationEndpoint** para migrar os objetos de contato. Durante a instalação herdada e o período de coexistência do Skype for Business Server 2019, os números de acesso discado que você criou no Skype for Business Server 2019 se comportam de forma semelhante aos números de acesso de discagem que você cria na instalação herdada, conforme descrito neste seção. 

Os números de acesso discado que você criou na instalação herdada, mas foram movidos para o Skype for Business Server 2019, ou que você criou no Skype for Business Server 2019 antes, durante ou após a migração, têm as seguintes características:

- Não aparecem nos convites para reunião do Office Communications Server 2007 R2 e na página número de acesso discada.

- Exibido na página herdada de reunião de instalação convites e número de acesso discada.

- Aparecem nos convites para reunião do Skype for Business Server 2019 e na página número de acesso discada.

- Não pode ser exibido ou modificado na ferramenta administrativa do Office Communications Server 2007 R2.

- Pode ser exibido e modificado no painel de controle de instalação herdada e no Shell de gerenciamento de instalação herdado.

- Pode ser visualizado e modificado no painel de controle do Skype for Business Server 2019 e no Shell de gerenciamento do Skype for Business Server 2019.

- Pode ser resequenciado na região usando o cmdlet Set-CsDialinConferencingAccessNumber com o parâmetro Priority.

Você deve concluir a migração dos números de acesso à discagem que apontam para o pool de instalação herdada antes de encerrar o pool de instalação herdado. Se você não concluir a migração do número de acesso discado conforme descrito no procedimento a seguir, as chamadas de entrada para os números de acesso falharão.

> [!IMPORTANT]
> Você deve executar esse procedimento antes de descomissionar o pool de instalação herdado. 

> [!NOTE]
> Recomendamos que você mova números de acesso discada quando o uso de rede for baixo, caso haja um curto período de interrupção do serviço. 

## <a name="to-identify-and-move-dial-in-access-numbers"></a>Para identificar e mover números de acesso discado

1. Inicie o Shell de gerenciamento do Skype for Business Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Skype for Business Server 2019**e, em seguida, clique em **Shell de gerenciamento do Skype for Business Server**.

2. Para mover cada número de acesso à discagem para um pool hospedado no Skype for Business Server 2019, a partir da linha de comando, execute: 

   ```PowerShell
   Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>
   ```

3. Abra o painel de controle do Skype for Business Server.

4. Na barra de navegação esquerda, clique em **Conferência**.

5. Clique na guia **número de acesso à discagem** . 

6. Verifique se os números de acesso de discagem permanecem para o pool de instalação herdado do qual você está migrando.

    > [!NOTE]
    > Quando todos os números de acesso discado apontam para o pool do Skype for Business Server 2019, você pode descomissionar o pool de instalação herdado. 

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-control-panel"></a>Verifique a migração do número de acesso discado usando o painel de controle do Skype for Business Server

1. Em uma conta de usuário que é atribuída à função **CsUserAdministrator** ou à função **CsAdministrator** , faça logon em qualquer computador na sua implantação interna. 

2. Abra o painel de controle do Skype for Business Server.

3. Na barra de navegação esquerda, clique em **Conferência**.

4. Clique na guia **número de acesso à discagem** . 

5. Verifique se todos os números de acesso de discagem foram migrados para o pool hospedado no Skype for Business Server 2019.

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-management-shell"></a>Verificar a migração do número de acesso discado usando o Shell de gerenciamento do Skype for Business Server

1. Abrir o Shell de gerenciamento do Skype for Business Server.

2. Para retornar todos os números de acesso de conferência discada migrados, a partir da linha de comando executar:

   ```PowerShell
   Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}
   ```

3. Verifique se todos os números de acesso de discagem foram migrados para o pool hospedado no Skype for Business Server 2019.


