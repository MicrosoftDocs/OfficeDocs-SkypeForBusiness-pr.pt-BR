---
title: Criar ou modificar um intervalo de órbitas do Estacionamento de Chamada Skype for Business
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 549ec118-eee5-4333-9416-80929ec057e0
description: Crie ou modifique uma tabela de intervalo de órbitas do Estacionamento de Chamada Skype for Business Server Enterprise Voice.
ms.openlocfilehash: ffe4a47a099099d31fdd55d23a95065549233f92
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60839693"
---
# <a name="create-or-modify-a-call-park-orbit-range-in-skype-for-business"></a>Criar ou modificar um intervalo de órbitas do Estacionamento de Chamada Skype for Business

Crie ou modifique uma tabela de intervalo de órbitas do Estacionamento de Chamada Skype for Business Server Enterprise Voice.

Call Park usa órbitas para chamadas de estacionamento. Antes que os usuários possam estacionar e recuperar chamadas, você deve configurar a tabela de órbita do Estacionamento de Chamadas. Você precisa especificar os intervalos de números de extensão (órbitas) que sua organização reserva para chamadas de estacionamento e definir o roteamento para esses intervalos especificando qual pool de Estacionamento de Chamadas lida com cada intervalo. Quando você define intervalos de órbitas, o objetivo é ter órbitas suficientes para que qualquer órbita não seja reutilizada muito rapidamente, mas não tantas órbitas que você limite o número de extensões disponíveis para usuários ou outros serviços. Você pode criar vários intervalos de órbita do Estacionamento de Chamada para cada pool Skype for Business Server onde o aplicativo Estacionamento de Chamada é implantado. Cada intervalo de órbitas do Estacionamento de Chamada deve ter um nome global exclusivo e um conjunto exclusivo de extensões.

> [!IMPORTANT]
> Normalmente, um intervalo de órbitas engloba 100 órbitas ou menos. Cada intervalo pode ser muito maior, contanto que seja menor do que o máximo de 10.000 órbitas por intervalo e tenha menos de 50.000 órbitas por pool. Se o intervalo for muito pequeno, as órbitas serão reutilizadas mais rapidamente.

Use blocos de extensões virtuais (extensões sem um usuário ou telefone atribuído a elas) para intervalos de órbita.

> [!NOTE]
> Não há suporte para a atribuição de números DID (Discagem direta interna) como números de órbita na tabela de órbita do Estacionamento de Chamada.

Utilize um dos seguintes procedimentos para criar ou modificar um intervalo de órbitas de estacionamento de chamada.

### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a>Para usar Skype for Business Server Painel de Controle para criar ou modificar um intervalo de números para chamadas de estacionamento

1. Faça logon no computador como membro do grupo RTCUniversalServerAdmins ou como membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte **Delegate Setup Permissions**.

2. Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle.

3. Na barra de navegação esquerda, clique em **Recursos de Voz** e em **Estacionamento de Chamada**.

4. Na página **Estacionamento de Chamada**, execute um dos seguintes procedimentos:

   - Para criar um novo intervalo de órbitas, clique em **Novo**. Em **Nome**, digite um nome de identificação para esse intervalo de números.

     > [!NOTE]
     > Após confirmar o intervalo de órbitas do banco de dados, não será possível alterar esse nome.

   - Para modificar um intervalo de órbitas existente, digite todo ou parte do nome do intervalo de órbitas no campo de pesquisa. Na lista de resultados de órbitas, clique na órbita que desejar, clique em **Editar** e clique em **Mostrar detalhes**.

5. No primeiro campo do **Intervalo numérico**, digite o número inicial do intervalo de extensões desta órbita de estacionamento de chamada e, no segundo campo **Intervalo numérico**, digite o número final do intervalo. Esteja ciente:

   - O número inicial do intervalo deve ser menor ou igual ao número final do intervalo.

   - O valor do número inicial do intervalo deve ter a mesma extensão que o número final do intervalo.

   - O intervalo da órbita deve ser único. Esse intervalo não pode se sobrepor a nenhum outro intervalo.

   - Se o intervalo de órbitas começar com o caractere \* ou #, o intervalo deve ser maior que 100.

   - Valores válidos: deve corresponder à cadeia de caracteres de expressão regular ([ \\ *|#]?[ 1-9]\d {0,7} )| ([1-9]\d {0,8} ). Isso significa que o valor deve ser uma cadeia de caracteres começando com o caractere ou # ou um \* número de 1 a 9 (o primeiro caractere não pode ser um zero). Se o primeiro caractere for ou #, o caractere a seguir deverá ser um \* número de 1 a 9 (não pode ser um zero). Os caracteres subsequentes podem ser qualquer número de 0 a 9 até sete caracteres adicionais (por exemplo, "#6000", " \* 92000", " 95551212" e \* "915551212"). Se o primeiro caractere não for ou #, o primeiro caractere deverá ser um número de 1 a 9 (não pode ser zero), seguido por até oito caracteres, cada um com um número de \* 0 a 9 (por exemplo, "915551212", "41212", "300").

   - Você não deve ter mais que um total de 50.000 órbitas por pool. Cada intervalo de órbita geralmente abrange 100 órbitas ou menos, mas pode ser muito maior, contanto que inclua menos que 10.000 órbitas. Por exemplo, em vez de especificar um número inicial em "7000000" e um número final em "8000000", considere especificar um número inicial em "7000000" e um número final em "7000100".

6. No **FQDN do servidor de destino**, clique no FQDN ou na ID do serviço de aplicativo que hospeda o aplicativo de Estacionamento de Chamada. Todas as chamadas estacionadas em números entre o intervalo especificado pelo número inicial e o número final no intervalo da órbita será roteado para esse servidor ou pool.

7. Clique em **Confirmar**.

### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a>Para usar Skype for Business Server Shell de Gerenciamento para criar ou modificar um intervalo de números para chamadas de estacionamento

1. Faça logoff no computador onde o Shell de Gerenciamento do Skype for Business Server está instalado como membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário **necessários** conforme descrito em Permissões de Instalação do Representante .

2. Inicie o shell Skype for Business Server gerenciamento: clique em **Iniciar,** clique em Todos os **Programas,** clique Skype for Business **2015** e clique **em Skype for Business Server Shell de Gerenciamento.**

3. Use o **New-CsCallParkOrbit** para criar um novo intervalo de números de órbitas. Use o **Set-CsCallParkOrbit** para modificar um intervalo de números de órbitas de estacionamento de chamada existente.

    Na linha de comando, execute:

   ```powershell
   New-CsCallParkOrbit -Identity <name of orbit range> -NumberRangeStart <first number in orbit range> -NumberRangeEnd <last number in orbit range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application>
   ```

    Por exemplo:

   ```powershell
   New-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1
   ```

    O seguinte exemplo mostra como modificar os números em intervalo de órbitas existente

   ```powershell
   Set-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 500 -NumberRangeEnd 699
   ```

## <a name="see-also"></a>Confira também

[New-CsCallParkOrbit](/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[Set-CsCallParkOrbit](/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[Excluir um intervalo de órbita de estacionamento de chamada](/previous-versions/office/lync-server-2013/lync-server-2013-delete-a-call-park-orbit-range)