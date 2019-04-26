---
title: Migrar números de acesso de discagem
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Migrar números de acesso de discagem para Skype para Business Server 2019 requer executando o cmdlet Move-CsApplicationEndpoint para migrar os objetos de contato. Durante o install herdado e Skype para Business Server 2019 período de coexistência, números de acesso de discagem que você criou em Skype for Business Server 2019 se comportam de forma semelhante aos números de acesso de discagem criados na instalar herdada, conforme descrito neste seção.
ms.openlocfilehash: 7f7aef113018a27e70b88e166d365195c07dce9c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32239580"
---
# <a name="migrate-dial-in-access-numbers"></a>Migrar números de acesso de discagem

Migrar números de acesso de discagem para Skype para Business Server 2019 requer executando o cmdlet **Move-CsApplicationEndpoint** para migrar os objetos de contato. Durante o install herdado e Skype para Business Server 2019 período de coexistência, números de acesso de discagem que você criou em Skype for Business Server 2019 se comportam de forma semelhante aos números de acesso de discagem criados na instalar herdada, conforme descrito neste seção. 

Números de acesso de discagem que você criou no antigo instalar, mas movidos para Skype para Business Server 2019 ou que você criou em Skype for Business 2019 de servidor antes, durante ou após a migração, têm as seguintes características:

- Não aparecem nos convites de reunião do Office Communications Server 2007 R2 e a página de número de acesso de discagem.

- Aparecem nos convites de reunião install herdado e página de número de acesso de discagem.

- Aparecem nos Skype para convites de reunião de negócios Server 2019 e página de número de acesso de discagem.

- Não podem ser exibidos ou modificados na ferramenta administrativa do Office Communications Server 2007 R2.

- Podem ser exibidos e modificados na instalar herdado painel de controle e na herdado instalar o Shell de gerenciamento.

- Podem ser exibidos e modificados no Skype para painel de controle do Business Server 2019 e no Skype do Shell de gerenciamento do Business Server 2019.

- Podem ser sequenciado novamente com a região usando o cmdlet Set-CsDialinConferencingAccessNumber com o parâmetro Priority.

Você deverá concluir a migrar os números de acesso de discagem que aponte para o antigo instalar pool antes de encerrar o pool herdado install. Se você não concluir a migração do número de acesso de discagem conforme descrito no procedimento a seguir, as chamadas de entrada para os números de acesso falhará.

> [!IMPORTANT]
> Você deve executar esse procedimento antes de encerrar o pool herdado install. 

> [!NOTE]
> É recomendável que você mova os números de acesso de discagem quando o uso da rede estiver baixo, caso haja um período curto de interrupção do serviço. 

## <a name="to-identify-and-move-dial-in-access-numbers"></a>Identificar e mover os números de acesso de discagem

1. Inicie o Skype do Shell de gerenciamento do servidor de negócios: clique em **Iniciar**, clique em **Todos os programas**, clique em **Microsoft Skype para Business Server 2019**e, em seguida, clique em **Skype do Shell de gerenciamento do servidor de negócios**.

2. Para mover cada número de acesso de discagem para um pool hospedado no Skype para Business Server 2019, a partir da linha de comando execute: 

   ```
   Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>
   ```

3. Abra o Skype para painel de controle do servidor de negócios.

4. Na barra de navegação esquerda, clique em **Conferência**.

5. Clique na guia **Número de acesso de discagem** . 

6. Verifique se não há números de acesso discado permanecem para o pool herdado install do qual você está migrando.

    > [!NOTE]
    > Quando todos os números de acesso de discagem aponta para o Skype para Business Server 2019 pool, você poderá encerrar o pool herdado install. 

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-control-panel"></a>Verifique se a migração de número de acesso de discagem usando o Skype para painel de controle do servidor de negócios

1. Usando uma conta de usuário atribuída à função **CsUserAdministrator** ou **csadministrator** , faça logon em qualquer computador em sua implantação interna. 

2. Abra o Skype para painel de controle do servidor de negócios.

3. Na barra de navegação esquerda, clique em **Conferência**.

4. Clique na guia **Número de acesso de discagem** . 

5. Verifique se que todos os números de acesso discado foram migrados para o pool hospedado no Skype para Business Server 2019.

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-management-shell"></a>Verifique se a migração de número de acesso de discagem usando o Skype do Shell de gerenciamento do servidor de negócios

1. Abra o Skype do Shell de gerenciamento do servidor de negócios.

2. Para retornar todos os números de acesso de conferência discada migrados, na linha de comando execute:

   ```
   Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}
   ```

3. Verifique se que todos os números de acesso discado foram migrados para o pool hospedado no Skype para Business Server 2019.


