---
title: Criar ou modificar uma faixa de opções de estacionamento de chamada no Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 549ec118-eee5-4333-9416-80929ec057e0
description: Crie ou modifique uma tabela de faixa de órbita de estacionamento de chamada no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: 77be47597e5bbb674719ac2b3192efdf4217a3dd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286260"
---
# <a name="create-or-modify-a-call-park-orbit-range-in-skype-for-business"></a>Criar ou modificar uma faixa de opções de estacionamento de chamada no Skype for Business

Crie ou modifique uma tabela de faixa de órbita de estacionamento de chamada no Skype for Business Server Enterprise Voice.

O parque de chamadas usa órbitas para chamadas de estacionamento. Para que os usuários possam estacionar e recuperar chamadas, você deve configurar a tabela órbita do parque de chamadas. Você precisa especificar os intervalos de números de ramal (órbitas) que a sua organização irá reservar para fazer chamadas de estacionamento e definir o roteamento para esses intervalos especificando qual o pool do estacionamento de chamadas manipula cada intervalo. Quando você define intervalos de órbita, a meta é ter órbitas suficientes para que qualquer uma das órbitas não seja reutilizada rapidamente, mas não muitas órbitas que você limite o número de extensões disponíveis para usuários ou outros serviços. Você pode criar várias faixas órbitas do estacionamento de chamada para cada pool do Skype for Business Server onde o aplicativo de estacionamento de chamada é implantado. Cada faixa de opções de estacionamento de chamadas deve ter um nome globalmente exclusivo e um conjunto exclusivo de extensões.

> [!IMPORTANT]
> Normalmente, um intervalo de órbitas engloba 100 órbitas ou menos. Cada intervalo pode ser muito maior, contanto que seja menor do que o máximo de 10.000 órbitas por intervalo e tenha menos de 50.000 órbitas por pool. Se o intervalo for muito pequeno, as órbitas serão reutilizadas mais rapidamente.

Use blocos de extensões virtuais (extensões sem um usuário ou telefone atribuído a elas) para intervalos de órbita.

> [!NOTE]
> Não há suporte para a atribuição de números do Direct Inward Dialing (DID) como números órbitas na tabela órbita do estacionamento de chamada.

Utilize um dos seguintes procedimentos para criar ou modificar um intervalo de órbitas de estacionamento de chamada.

### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a>Para usar o painel de controle do Skype for Business Server para criar ou modificar um intervalo de números para chamadas de estacionamento

1. Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como um membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte **Delegate Setup Permissions**.

2. Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.

3. Na barra de navegação esquerda, clique em **Recursos de Voz** e em **Estacionamento de Chamada(Call Park)**.

4. Na página **Estacionamento de Chamada**, execute um dos seguintes procedimentos:

   - Para criar um novo intervalo de órbitas, clique em **Novo**. Em **Nome**, digite um nome de identificação para esse intervalo de números.

     > [!NOTE]
     > Após confirmar o intervalo de órbitas do banco de dados, não será possível alterar esse nome.

   - Para modificar um intervalo de órbitas existente, digite todo ou parte do nome do intervalo de órbitas no campo de pesquisa. Na lista de resultados de órbitas, clique na órbita que desejar, clique em **Editar** e clique em **Mostrar detalhes**.

5. No primeiro campo do **Intervalo numérico**, digite o número inicial do intervalo de extensões desta órbita de estacionamento de chamada e, no segundo campo **Intervalo numérico**, digite o número final do intervalo. Lembre-se:

   - O número inicial do intervalo deve ser menor ou igual ao número final.

   - O valor do número inicial do intervalo deve ter o mesmo comprimento que o número final do intervalo.

   - O intervalo de órbita deve ser exclusivo. Este intervalo não pode sobrepor outro intervalo.

   - Se o intervalo de órbita começar com o \* caractere ou #, o intervalo deve ser maior que 100.

   - Valores válidos: devem corresponder à cadeia de caracteres de expressão\\regular ([* | #] ? [1-{0,7}9] \d) | ([1-9] \d{0,8}). Isso significa que o valor deve ser uma cadeia de caracteres que comece \* com o caractere ou # ou um número de 1 a 9 (o primeiro caractere não pode ser zero). Se o primeiro caractere for \* ou #, o seguinte caractere deve ser um número de 1 a 9 (não pode ser zero). Os caracteres subsequentes podem ser qualquer número de 0 a 9 até sete caracteres adicionais (por exemplo, "#6000"\*, "92000"\*, "95551212" e "915551212"). Se o primeiro caractere não \* for ou #, o primeiro caractere deve ser um número de 1 a 9 (não pode ser zero), seguido por até oito caracteres, cada um dos números de 0 a 9 (por exemplo, "915551212", "41212", "300").

   - Você não deve ter mais do que um total de 50.000 órbitas por pool. Cada intervalo de órbita geralmente possui 100 ou menos órbitas, mas pode ser muito maior contanto que inclua menos do que 10.000 órbitas. Por exemplo, ao invés de especificar um número inicial de "7000000" e um número final de "8000000," considere especificar um número inicial de "7000000" e um número final de "7000100."

6. Em **FQDN do servidor de destino**, clique no nome de domínio totalmente qualificado (FQDN) ou ID de serviço do serviço de aplicativo que hospeda o aplicativo parque de chamadas. Todas as chamadas estacionadas em números dentro do intervalo especificado pelo número inicial e número final do intervalo de órbita serão direcionadas para este servidor ou pool.

7. Clique em **Confirmar**.

### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a>Para usar o Shell de gerenciamento do Skype for Business Server para criar ou modificar um intervalo de números para chamadas de estacionamento

1. Faça logon no computador em que o Shell de gerenciamento do Skype for Business Server está instalado como membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário necessários, conforme descrito em **permissões de configuração do representante**.

2. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.

3. Use o **New-CsCallParkOrbit** para criar um novo intervalo de números de órbitas. Use o **Set-CsCallParkOrbit** para modificar um intervalo de números de órbitas de estacionamento de chamada existente.

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

## <a name="see-also"></a>Confira também

[New-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[Excluir uma faixa de opções de estacionamento de chamada](https://technet.microsoft.com/library/85e9f916-062d-450d-ac0a-aeaefc0f7cdc.aspx)
