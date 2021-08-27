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
ms.localizationpriority: medium
description: Migrar números de acesso discado para Skype for Business Server 2019 requer a execução do cmdlet Move-CsApplicationEndpoint para migrar os objetos de contato. Durante a instalação herdado e o período de coexistência do Skype for Business Server 2019, os números de acesso discado que você criou no Skype for Business Server 2019 se comportam da mesma forma com os números de acesso discado que você cria na instalação herdado, conforme descrito nesta seção.
ms.openlocfilehash: 4d5d0ad88c241685e7ea86c7adc9dc536d3180a8
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58589331"
---
# <a name="migrate-dial-in-access-numbers"></a>Migrar os números de acesso discado

Migrar números de acesso discado para o Skype for Business Server 2019 requer a execução do cmdlet **Move-CsApplicationEndpoint** para migrar os objetos de contato. Durante a instalação herdado e o período de coexistência do Skype for Business Server 2019, os números de acesso discado que você criou no Skype for Business Server 2019 se comportam da mesma forma com os números de acesso discado que você cria na instalação herdado, conforme descrito nesta seção. 

Os números de acesso discado criados na instalação herdado, mas movidos para o Skype for Business Server 2019 ou que você criou no Skype for Business Server 2019 antes, durante ou após a migração, têm as seguintes características:

- Não apareça nos Office de reunião do Communications Server 2007 R2 e na página número de acesso discado.

- Apareça na página de número de acesso de instalação herdado e convites de reunião de instalação herdado.

- Apareça nos Skype for Business Server de reunião 2019 e na página número de acesso discado.

- Não é possível ser exibido ou modificado na ferramenta administrativa Office Communications Server 2007 R2.

- Pode ser visualizado e modificado no Painel de Controle de instalação herdado e no Shell de Gerenciamento de instalação herdado.

- Pode ser visualizado e modificado no Painel de Controle Skype for Business Server 2019 e no Shell de Gerenciamento Skype for Business Server 2019.

- Pode ser re-sequenciado dentro da região usando o cmdlet Set-CsDialinConferencingAccessNumber com o parâmetro Priority.

Você deve concluir a migração de números de acesso discado que apontem para o pool de instalação herdado antes de encerrar o pool de instalação herdado. Se você não concluir a migração de número de acesso discado conforme descrito no procedimento a seguir, as chamadas de entrada para os números de acesso falharão.

> [!IMPORTANT]
> Você deve executar este procedimento antes de desmantelar o pool de instalação herdável. 

> [!NOTE]
> Recomendamos que você mova números de acesso discado quando o uso da rede estiver baixo, caso haja um curto período de paralisação do serviço. 

## <a name="to-identify-and-move-dial-in-access-numbers"></a>Para identificar e mover números de acesso discado

1. Inicie o shell Skype for Business Server gerenciamento: clique em **Iniciar,** clique em Todos os **Programas,** clique em **Microsoft Skype for Business Server 2019** e clique em Skype for Business Server **Shell de Gerenciamento.**

2. Para mover cada número de acesso discado para um pool hospedado no Skype for Business Server 2019, a partir da linha de comando executar: 

   ```PowerShell
   Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>
   ```

3. Abra Skype for Business Server Painel de Controle.

4. Na barra de navegação esquerda, clique em **Conferência**.

5. Clique na **guia Número de Acesso Discado.** 

6. Verifique se nenhum número de acesso discado permanece para o pool de instalação herdado do qual você está migrando.

    > [!NOTE]
    > Quando todos os números de acesso discado apontarem para o pool de Skype for Business Server 2019, você poderá desmantelar o pool de instalação herdado. 

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-control-panel"></a>Verificar a migração de número de acesso discado usando Skype for Business Server Painel de Controle

1. Em uma conta de usuário atribuída à função **CsUserAdministrator** ou à **função CsAdministrator,** faça logon em qualquer computador em sua implantação interna. 

2. Abra Skype for Business Server Painel de Controle.

3. Na barra de navegação esquerda, clique em **Conferência**.

4. Clique na **guia Número de Acesso Discado.** 

5. Verifique se todos os números de acesso discado são migrados para o pool hospedado no Skype for Business Server 2019.

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-management-shell"></a>Verificar a migração de número de acesso discado usando Skype for Business Server Shell de Gerenciamento

1. Abra Skype for Business Server Shell de Gerenciamento.

2. Para retornar todos os números de acesso de conferência discado migrados, a partir da linha de comando, execute:

   ```PowerShell
   Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}
   ```

3. Verifique se todos os números de acesso discado são migrados para o pool hospedado no Skype for Business Server 2019.


