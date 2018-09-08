---
title: Criar ou modificar um intervalo de órbita de estacionamento de chamada no Skype para negócios
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 549ec118-eee5-4333-9416-80929ec057e0
description: Criar ou modificar uma tabela de intervalo de órbita de estacionamento de chamada no Skype para Business Server Enterprise Voice.
ms.openlocfilehash: 8c9ff275e384148fb6e40f96bd26e7273809f25a
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23883877"
---
# <a name="create-or-modify-a-call-park-orbit-range-in-skype-for-business"></a>Criar ou modificar um intervalo de órbita de estacionamento de chamada no Skype para negócios

Criar ou modificar uma tabela de intervalo de órbita de estacionamento de chamada no Skype para Business Server Enterprise Voice.

Estacionamento de chamadas usa Órbitas de estacionamento de chamadas. Antes que os usuários podem estacionar e recuperar chamadas, você deve configurar a tabela de órbita de estacionamento de chamadas. Você precisa especificar os intervalos de números de ramal (Órbitas) que a sua organização reservar para estacionamento de chamadas e definir o roteamento para esses intervalos especificando qual pool de estacionamento de chamada lida com cada intervalo. Quando você definir intervalos de órbita, o objetivo é ter suficiente Órbitas para que qualquer uma órbita não seja reutilizada muito rapidamente, mas não tantas Órbitas que você limite o número de extensões disponíveis para usuários ou outros serviços. Você pode criar vários intervalos de órbita de estacionamento de chamadas para cada Skype para pool de servidores de negócios, onde o aplicativo de estacionamento de chamada é implantado. Cada intervalo de órbita de estacionamento de chamada deve ter um nome globalmente exclusivo e um conjunto exclusivo de extensões.

> [!IMPORTANT]
> Normalmente, um intervalo de órbitas engloba 100 órbitas ou menos. Cada intervalo pode ser muito maior, contanto que seja menor do que o máximo de 10.000 órbitas por intervalo e tenha menos de 50.000 órbitas por pool. Se o intervalo for muito pequeno, as órbitas serão reutilizadas mais rapidamente.

Use blocos de extensões virtuais (extensões sem um usuário ou telefone atribuído a elas) para intervalos de órbita.

> [!NOTE]
> Tabela de órbita atribuir números de Direct Inward Dialing (DID) como números de órbita de estacionamento de chamada não é suportada.

Utilize um dos seguintes procedimentos para criar ou modificar um intervalo de órbitas de estacionamento de chamada.

### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a>Usar Skype para painel de controle do Business Server para criar ou modificar um intervalo de números para estacionamento de chamadas

1. Faça logon no computador como membro do grupo RTCUniversalServerAdmins ou como um membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte **Delegate Setup Permissions**.

2. Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.

3. Na barra de navegação esquerda, clique em **Recursos de Voz** e em **Estacionamento de Chamada(Call Park)**.

4. Na página **Estacionamento de Chamada**, execute um dos seguintes procedimentos:

  - Para criar um novo intervalo de órbitas, clique em **Novo**. Em **Nome**, digite um nome de identificação para esse intervalo de números.

    > [!NOTE]
    > Após confirmar o intervalo de órbitas do banco de dados, não será possível alterar esse nome.

  - Para modificar um intervalo de órbitas existente, digite todo ou parte do nome do intervalo de órbitas no campo de pesquisa. Na lista de resultados de órbitas, clique na órbita que desejar, clique em **Editar** e clique em **Mostrar detalhes**.

5. No primeiro campo do **Intervalo numérico**, digite o número inicial do intervalo de extensões desta órbita de estacionamento de chamada e, no segundo campo **Intervalo numérico**, digite o número final do intervalo. Tenha em mente:

   - O número inicial do intervalo deve ser menor ou igual ao número final.

   - O valor do número inicial do intervalo deve ter o mesmo comprimento que o número final do intervalo.

   - O intervalo de órbita deve ser exclusivo. Este intervalo não pode sobrepor outro intervalo.

   - Se o intervalo de órbita começa com o caractere \* ou #, o intervalo deve ser maior que 100.

   - Valores válidos: deve coincidir com a cadeia de caracteres de expressão regular ([\\* | #] ? [1-9] \d{0,7}) | ([1-9] \d{0,8}). Isso significa que o valor deve ser uma cadeia de caracteres iniciada com o caractere \* ou #, ou um número entre 1 e 9 (o primeiro caractere não pode ser um zero). Se o primeiro caractere for \* ou #, o caractere seguinte deve ser um número entre 1 e 9 (ele não pode ser um zero). Os caracteres subsequentes podem ser qualquer número entre 0 e 9 até sete caracteres adicionais (por exemplo, "#6000", "\*92000", "\*95551212" e "915551212"). Se o primeiro caractere não for \* ou #, o primeiro caractere deve ser um número entre 1 e 9 (ele não pode ser zero), seguido por até oito caracteres, cada um número entre 0 e 9 (por exemplo, "915551212", "41212", "300").

   - Você não deve ter mais do que um total de 50.000 órbitas por pool. Cada intervalo de órbita geralmente possui 100 ou menos órbitas, mas pode ser muito maior contanto que inclua menos do que 10.000 órbitas. Por exemplo, ao invés de especificar um número inicial de "7000000" e um número final de "8000000," considere especificar um número inicial de "7000000" e um número final de "7000100."

6. Em **FQDN do servidor de destino**, clique no nome de domínio totalmente qualificado (FQDN) ou ID de serviço do serviço aplicativo que hospeda o aplicativo de estacionamento de chamadas. Todas as chamadas estacionadas em números dentro do intervalo especificado pelo número inicial e número final do intervalo de órbita serão direcionadas para este servidor ou pool.

7. Clique em **Confirmar**.

### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a>Usar Skype para Business Server Management Shell para criar ou modificar um intervalo de números para estacionamento de chamadas

1. Faça logon no computador onde o Skype do Shell de gerenciamento do servidor de negócios está instalado como membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário necessários, conforme descrito em **Delegate Setup Permissions**.

2. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.

3. Use o **New-CsCallParkOrbit** para criar um novo intervalo de números de órbita. Use o **Set-CsCallParkOrbit** para modificar um intervalo existente de números de órbita.

    Na linha de comando, execute:

   ```
   New-CsCallParkOrbit -Identity <name of orbit range> -NumberRangeStart <first number in orbit range> -NumberRangeEnd <last number in orbit range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application>
   ```

    Por exemplo:

   ```
   New-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1
   ```

    O seguinte exemplo mostra como modificar os números em intervalo de órbitas existente

   ```
   Set-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 500 -NumberRangeEnd 699
   ```

## <a name="see-also"></a>Consulte também

[New-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[Excluir um intervalo de órbita de estacionamento de chamada](https://technet.microsoft.com/library/85e9f916-062d-450d-ac0a-aeaefc0f7cdc.aspx)