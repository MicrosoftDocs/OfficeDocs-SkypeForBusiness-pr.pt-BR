---
title: Migrar os números de acesso discado
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Migrar números de acesso de discagem para o Skype for Business Server 2019 requer a execução do cmdlet Move-CsApplicationEndpoint para migrar os objetos de contato. Durante o período de coexistência de instalação herdada e Skype for Business Server 2019, os números de acesso de discagem criados no Skype for Business Server 2019 se comportam de forma semelhante aos números de acesso de discagem que você cria na instalação herdada, conforme descrito nesta seção.
ms.openlocfilehash: 0df71debe8a6d5c686d8bce17b837f32a4ca2bab
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752693"
---
# <a name="migrate-dial-in-access-numbers"></a>Migrar os números de acesso discado

Migrar números de acesso de discagem para o Skype for Business Server 2019 requer a execução do cmdlet **move-CsApplicationEndpoint** para migrar os objetos de contato. Durante o período de coexistência de instalação herdada e Skype for Business Server 2019, os números de acesso de discagem criados no Skype for Business Server 2019 se comportam de forma semelhante aos números de acesso de discagem que você cria na instalação herdada, conforme descrito nesta seção. 

Os números de acesso de discagem que você criou na instalação herdada, mas movidos para o Skype for Business Server 2019, ou que você criou no Skype for Business Server 2019 antes, durante ou após a migração, têm as seguintes características:

- Não aparecem nos convites de reunião do Office Communications Server 2007 R2 e na página número de acesso de discagem.

- Aparecem nos convites de reunião de instalação herdados e na página número de acesso de discagem.

- Aparecem nos convites de reunião do Skype for Business Server 2019 e na página número de acesso de discagem.

- Não podem ser exibidos ou modificados na ferramenta administrativa do Office Communications Server 2007 R2.

- Pode ser exibido e modificado no painel de controle de instalação herdado e no Shell de gerenciamento de instalação herdado.

- Pode ser exibido e modificado no painel de controle do Skype for Business Server 2019 e no Shell de gerenciamento do Skype for Business Server 2019.

- Podem ser seqüenciados novamente dentro da região usando o cmdlet Set-CsDialinConferencingAccessNumber com o parâmetro Priority.

Você deve concluir a migração dos números de acesso de discagem que apontam para o pool de instalação herdado antes de encerrar o pool de instalação herdado. Se você não concluir a migração do número de acesso de discagem, conforme descrito no procedimento a seguir, as chamadas de entrada para os números de acesso falharão.

> [!IMPORTANT]
> Você deve executar esse procedimento antes de encerrar o pool de instalação herdado. 

> [!NOTE]
> Recomendamos que você mova os números de acesso de discagem quando o uso da rede estiver baixo, caso haja uma breve interrupção no serviço. 

## <a name="to-identify-and-move-dial-in-access-numbers"></a>Para identificar e mover os números de acesso de discagem

1. Inicie o Shell de gerenciamento do Skype for Business Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Skype for Business Server 2019**e em **Shell de gerenciamento do Skype for Business Server**.

2. Para mover cada número de acesso de discagem para um pool hospedado no Skype for Business Server 2019, na linha de comando, execute: 

   ```PowerShell
   Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>
   ```

3. Abra o painel de controle do Skype for Business Server.

4. Na barra de navegação esquerda, clique em **Conferência**.

5. Clique na guia **número de acesso de discagem** . 

6. Verifique se os números de acesso de discagem permanecem para o pool de instalação herdado do qual você está migrando.

    > [!NOTE]
    > Quando todos os números de acesso de discagem apontarem para o pool do Skype for Business Server 2019, você poderá encerrar o pool de instalação herdado. 

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-control-panel"></a>Verificar a migração do número de acesso de discagem usando o painel de controle do Skype for Business Server

1. A partir de uma conta de usuário atribuída à função **CsUserAdministrator** ou à função **CsAdministrator** , faça logon em qualquer computador em sua implantação interna. 

2. Abra o painel de controle do Skype for Business Server.

3. Na barra de navegação esquerda, clique em **Conferência**.

4. Clique na guia **número de acesso de discagem** . 

5. Verifique se todos os números de acesso de discagem foram migrados para o pool hospedado no Skype for Business Server 2019.

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-management-shell"></a>Verificar a migração do número de acesso de discagem usando o Shell de gerenciamento do Skype for Business Server

1. Abra o Shell de gerenciamento do Skype for Business Server.

2. Para retornar todos os números de acesso de conferência discada migrados, a partir da linha de comando, execute:

   ```PowerShell
   Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}
   ```

3. Verifique se todos os números de acesso de discagem foram migrados para o pool hospedado no Skype for Business Server 2019.


