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
description: Migrar números de acesso discado para o Skype for Business Server 2019 requer a execução do cmdlet Move-CsApplicationEndpoint para migrar os objetos de contato. Durante a instalação herdada e o período de coexistência do Skype for Business Server 2019, os números de acesso de discagem criados no Skype for Business Server 2019 se comportam de forma semelhante aos números de acesso de discagem criados na instalação herdada, conforme descrito nesta seção.
ms.openlocfilehash: 0df71debe8a6d5c686d8bce17b837f32a4ca2bab
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752693"
---
# <a name="migrate-dial-in-access-numbers"></a>Migrar os números de acesso discado

Migrar números de acesso discado para o Skype for Business Server 2019 requer a execução do cmdlet **Move-CsApplicationEndpoint** para migrar os objetos de contato. Durante a instalação herdada e o período de coexistência do Skype for Business Server 2019, os números de acesso de discagem criados no Skype for Business Server 2019 se comportam de forma semelhante aos números de acesso de discagem criados na instalação herdada, conforme descrito nesta seção. 

Os números de acesso de discagem criados na instalação herdada, mas migrados para o Skype for Business Server 2019, ou criados no Skype for Business Server 2019 antes, durante ou após a migração, têm as seguintes características:

- Não aparecem nos convites de reunião do Office Communications Server 2007 R2 e na página de número de acesso de discagem.

- Aparecem nos convites de reunião de instalação herdado e na página de número de acesso de discagem.

- Aparecem nos convites de reunião do Skype for Business Server 2019 e na página de número de acesso de discagem.

- Não pode ser visualizado ou modificado na ferramenta administrativa do Office Communications Server 2007 R2.

- Pode ser visualizado e modificado no Painel de Controle de instalação herdado e no Shell de Gerenciamento de instalação herdado.

- Pode ser visualizada e modificada no Painel de Controle do Skype for Business Server 2019 e no Shell de Gerenciamento do Skype for Business Server 2019.

- Pode ser sequenciado dentro da região usando o cmdlet Set-CsDialinConferencingAccessNumber com o parâmetro Priority.

Você deve concluir a migração dos números de acesso discado que apontam para o pool de instalação herdado antes de encerrar o pool de instalação herdado. Se você não concluir a migração do número de acesso de discagem conforme descrito no procedimento a seguir, as chamadas de entrada para os números de acesso falharão.

> [!IMPORTANT]
> Você deve executar este procedimento antes de descomissionar o pool de instalação herdável. 

> [!NOTE]
> Recomendamos que você mova os números de acesso de discagem quando o uso da rede estiver baixo, caso haja um curto período de insoqueção do serviço. 

## <a name="to-identify-and-move-dial-in-access-numbers"></a>Para identificar e mover números de acesso discado

1. Inicie o Shell de Gerenciamento do Skype for Business Server: Clique em **Iniciar,** Em Todos os **Programas,** clique em **Microsoft Skype for Business Server 2019** e, em seguida, clique no Shell de Gerenciamento do **Skype for Business Server.**

2. Para mover cada número de acesso de discagem para um pool hospedado no Skype for Business Server 2019, a partir da linha de comando, execute: 

   ```PowerShell
   Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>
   ```

3. Abra o Painel de Controle do Skype for Business Server.

4. Na barra de navegação esquerda, clique em **Conferência**.

5. Clique na **guia Número de Acesso de Discagem.** 

6. Verifique se não há números de acesso discado para o pool de instalação herdado do qual você está migrando.

    > [!NOTE]
    > Quando todos os números de acesso discado apontarem para o pool do Skype for Business Server 2019, você poderá descomissionar o pool de instalação herdado. 

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-control-panel"></a>Verificar a migração do número de acesso de discagem usando o Painel de Controle do Skype for Business Server

1. Em uma conta de usuário atribuída à função **CsUserAdministrator** ou **CsAdministrator,** faça logon em qualquer computador em sua implantação interna. 

2. Abra o Painel de Controle do Skype for Business Server.

3. Na barra de navegação esquerda, clique em **Conferência**.

4. Clique na **guia Número de Acesso de Discagem.** 

5. Verifique se todos os números de acesso discado são migrados para o pool hospedado no Skype for Business Server 2019.

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-management-shell"></a>Verificar a migração do número de acesso de discagem usando o Shell de Gerenciamento do Skype for Business Server

1. Abra o Shell de Gerenciamento do Skype for Business Server.

2. Para retornar todos os números de acesso de conferência discado migrados, execute a partir da linha de comando:

   ```PowerShell
   Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}
   ```

3. Verifique se todos os números de acesso discado são migrados para o pool hospedado no Skype for Business Server 2019.


