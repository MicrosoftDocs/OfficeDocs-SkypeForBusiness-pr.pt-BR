---
title: Criar ou modificar um intervalo de números não atribuídos Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
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
ms.assetid: a102b226-0460-4d5c-82f9-79b8444fa958
description: Crie, modifique ou exclua intervalos de números não atribuídos para o aplicativo Announcement Skype for Business Server Enterprise Voice. Isso afeta como as chamadas para números não atribuídos são manipuladas.
ms.openlocfilehash: 10e65d6202babd0c15fe569c71f6e8a84b301eb7
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62410544"
---
# <a name="create-or-modify-an-unassigned-number-range-in-skype-for-business-server"></a>Criar ou modificar um intervalo de números não atribuídos Skype for Business Server
 
Crie, modifique ou exclua intervalos de números não atribuídos para o aplicativo Announcement Skype for Business Server Enterprise Voice. Isso afeta como as chamadas para números não atribuídos são manipuladas.
  
Skype for Business Server permite que você diga o que acontece com chamadas de entrada para números de telefone válidos para sua organização, mas não são atribuídas a um usuário ou telefone. Para lidar com essas chamadas, você configura uma tabela de números não atribuídos. Você pode usar a tabela para rotear as chamadas para um aplicativo de Comunicado ou para um Exchange um servidor de UM.
  
O modo como você configura a tabela de números não atribuída depende de como você deseja usá-la. É possível configurar a tabela com todas as extensões válidas para sua organização, com apenas extensões não atribuídas ou com uma combinação de ambos os tipos de números. A tabela de números não atribuída pode incluir números atribuídos e não atribuídos, mas é chamada somente quando um chamador disca um número que não está atribuído no momento. Se você incluir todas as extensões válidas na tabela de números não atribuída, você poderá especificar a ação que ocorre sempre que alguém deixa sua organização, sem a necessidade de reconfigurar a tabela. Se você incluir extensões não atribuídas na tabela, poderá personalizar a ação que ocorre para números específicos. Por exemplo, se você alterar a extensão para seu atendimento ao cliente, poderá incluir o número antigo de atendimento ao cliente na tabela, e atribui-lo a um anúncio que fornece o novo número.
  
## <a name="configure-unassigned-phone-numbers"></a>Configurar números de telefone não atribuídos

Use um dos procedimentos a seguir para configurar intervalos de números não atribuídos para o aplicativo Comunicado.
  
> [!IMPORTANT]
> Antes de configurar a tabela de números não atribuídos, seu sistema já deve ter Comunicados definidos ou uma Exchange unificação de mensagens (UM) Atendedor Automático configurada. 
  
> [!TIP]
> Quando alguém chama um número não atribuído, Skype for Business Server pesquisa a tabela de números não atribuídos de cima para baixo e usa o primeiro intervalo correspondente. Portanto, uma ação que você deseja executar como última alternativa deve ser especificada para o último intervalo na tabela. 
  
### <a name="to-use-skype-for-business-server-control-panel-to-configure-unassigned-phone-numbers"></a>Para usar Skype for Business Server Painel de Controle para configurar números de telefone não atribuídos

1. Faça logon no computador como membro do grupo RTCUniversalServerAdmins ou como membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte **Delegate Setup Permissions**.
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle.  
    
3. Na barra de navegação esquerda, clique em **Recursos de Voz** e clique em **Número Não Atribuído**.
    
4. Na página **Número Não Atribuído** , faça um dos seguintes:
    
   - Para criar um novo intervalo de números, clique em **Novo**. Em **Nome**, digite um nome de identificação para esse intervalo de números.
    
     > [!NOTE]
     > Depois de comprometer o novo intervalo de números não atribuídos ao banco de dados, não é possível alterar esse nome. 
  
   - Para modificar um intervalo de números existente, digite todo ou parte do nome do intervalo de números no campo de pesquisa. Na lista resultante de intervalos de números, clique no nome que deseja, clique em **Editar** e em **Mostrar detalhes**.
    
5. No primeiro campo **Intervalo de números** digite o número inicial do intervalo, e no segundo campo **Intervalo de números** digite o número final.
    
   - O número inicial do intervalo deve ser menor ou igual ao número final.
    
   - Se o número inicial do intervalo ou o número final do intervalo incluir um número de extensão, os números inicial e final do intervalo precisarão incluir uma extensão e o número de extensão deverá ser o mesmo para os números inicial e final.
    
   - O número deve corresponder à expressão regular `(tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?`. Isso significa que `tel:` o número pode começar com a cadeia de caracteres (se você não especificar essa cadeia de caracteres, ele será adicionado automaticamente para você), um sinal de a mais (+) e um dígito de 1 a 9. O número de telefone pode ter até 17 dígitos e pode ser seguido de um ramal no formato ;ext=, seguido do número do ramal.
    
6. Em **Serviço de anúncio**, siga um destes procedimentos: 
    
   - Clique em **Comunicado**.
    
   - Click **UM do Exchange**.
    
7. Se, na etapa prévia, você clicou em **Comunicado**, faça o seguinte
    
    a. Em **FQDN do servidor de destino**, clique em **Selecionar**, clique no ID de serviço do serviço do Aplicativo que executa o aplicativo de Comunicado que manipulará as chamadas de entrada para esse intervalo de números não atribuídos e clique em **OK**.
    
    b. **Comunicado**, clique no comunicado que será reproduzido para esse intervalo de números não atribuídos.
    
8. Se, na etapa prévia, você clicou em **UM do Exchange**, em **Número de telefone do Atendedor Automático**, clique em **Selecionar**, clique no número de telefone que será usado para esse intervalo de números não atribuídos e clique em **OK**.
    
9. Clique em **OK**.
    
10. Na página **Número Não Atribuído** , certifique-se de que os intervalos de números não atribuídos sejam organizados na ordem que você deseja. Para alterar a posição de um intervalo na tabela, clique em um ou mais nomes consecutivos na lista de intervalos e clique na seta para cima ou na seta para baixo.
    
    > [!TIP]
    > Skype for Business Server pesquisa a tabela de números não atribuídos de cima para baixo e usa o primeiro intervalo que corresponde ao número não atribuído. Se você tiver intervalos sobrepostos e um intervalo especificar uma ação de último recurso, certifique-se de que o intervalo está na parte inferior da lista. 
  
11. Quando você tiver os intervalos de números não atribuídos na ordem que deseja, clique em **Comprometer tudo**.
    
### <a name="to-use-skype-for-business-server-management-shell-to-configure-unassigned-phone-numbers"></a>Para usar Skype for Business Server Shell de Gerenciamento para configurar números de telefone não atribuídos

1. Faça logoff no computador onde o Shell de Gerenciamento do Skype for Business Server está instalado como membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário **necessários**, conforme descrito em Permissões de Instalação do Representante.
    
2. Inicie o shell Skype for Business Server gerenciamento: clique em **Iniciar, em** Todos os **Programas, em** Skype for Business **2015** e em Skype for Business Server **Gerenciamento**.
    
3. Use **New-CsUnassignedNumber** para criar um novo intervalo de números não atribuídos. Use **Set-CsUnassignedNumber** para modificar um intervalo de números não atribuídos existente.
    
    > [!TIP]
    > Se você tiver intervalos sobrepostos e quiser que os intervalos sejam aplicados em uma ordem específica, inclua o parâmetro Priority. O intervalo com a maior prioridade será aplicado à chamada. O valor 0 representa a prioridade mais alta.
  
    Na linha de comando, faça um dos seguintes:
    
   - Para criar um intervalo de números para um serviço de Comunicado, execute:
    
     ```powershell
     New-CsUnassignedNumber -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -AnnouncementName <announcement name> -AnnouncementService <FQDN or service ID of the Announcement service>
     ```

   - Ou, para criar um intervalo de números para Exchange UM Atendedor Automático, execute:
    
     ```powershell
     New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber <phone number> -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range>
     ```

     Por exemplo:
    
     ```powershell
     New-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100" -AnnouncementName "Welcome Announcement" -AnnouncementService ApplicationServer:Redmond.contoso.com
     ```

     Ou
    
     ```powershell
     New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber "+12065551234" -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100"
     ```

     O exemplo a seguir mostra como modificar os números em um intervalo de números não atribuídos existente:
    
     ```powershell
     Set-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551900"
     ```

## <a name="delete-an-unnasigned-number-range"></a>Excluir um intervalo de números não assinados

### <a name="to-use-skype-for-business-server-control-panel-to-delete-an-unassigned-number-range"></a>Para usar Skype for Business Server Painel de Controle para excluir um intervalo de números não atribuídos

1.  Faça logon no computador como membro do grupo RTCUniversalServerAdmins ou como membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte **Delegate Setup Permissions**.
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle.  
    
3. Na barra de navegação à esquerda, clique em **Recursos de Voz** e em **Número Não Atribuído**.
    
4. Na página **Número Não Atribuído**, no campo de pesquisa, digite todo ou parte do nome do intervalo numérico não atribuído que deseja excluir.
    
5. Na lista de resultados de intervalos de número, clique no nome, clique em **Editar** e depois, clique em **Excluir**.
    
6. Clique em **Confirmar tudo**.
    
### <a name="to-use-skype-for-business-server-management-shell-to-delete-an-unassigned-number-range"></a>Para usar Skype for Business Server Shell de Gerenciamento para excluir um intervalo de números não atribuídos

1. Faça logoff no computador onde o Shell de Gerenciamento do Skype for Business Server está instalado como membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário **necessários**, conforme descrito em Permissões de Instalação do Representante.
    
2. Inicie o shell Skype for Business Server gerenciamento: clique em **Iniciar, em** Todos os **Programas, em** Skype for Business **2015** e em Skype for Business Server **Gerenciamento**.
    
3. Na linha de comando, digite:
    
   ```powershell
   Remove-CsUnassignedNumber -Identity "<name of unassigned number range>" 
   ```

    Por exemplo:
    
   ```powershell
   Remove-CsUnassignedNumber -Identity "Unassigned range 1"
   ```

    > [!NOTE]
    > Para obter detalhes sobre mais opções, [consulte Remove-CsCallParkOrbit](/powershell/module/skype/remove-cscallparkorbit?view=skype-ps). 
  
## <a name="see-also"></a>Confira também

[New-CsUnassignedNumber](/powershell/module/skype/new-csunassignednumber?view=skype-ps)
  
[Set-CsUnassignedNumber](/powershell/module/skype/set-csunassignednumber?view=skype-ps)
  
[Get-CsUnassignedNumber](/powershell/module/skype/get-csunassignednumber?view=skype-ps)