---
title: Criar ou modificar um intervalo de números não atribuído no Skype para Business Server
ms.reviewer: ''
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
ms.assetid: a102b226-0460-4d5c-82f9-79b8444fa958
description: Criar, modificar ou excluir intervalos de números não atribuídos para o aplicativo de anúncio no Skype para Business Server Enterprise Voice. Isso afeta o modo como nas chamadas para números não atribuídos são administradas.
ms.openlocfilehash: 9546e4caaab30ae7582866dbcefd680b04de33f2
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30872892"
---
# <a name="create-or-modify-an-unassigned-number-range-in-skype-for-business-server"></a>Criar ou modificar um intervalo de números não atribuído no Skype para Business Server
 
Criar, modificar ou excluir intervalos de números não atribuídos para o aplicativo de anúncio no Skype para Business Server Enterprise Voice. Isso afeta o modo como nas chamadas para números não atribuídos são administradas.
  
Skype para Business Server permite que você quer dizer que o que acontece às chamadas recebidas para números de telefone são válidos para a sua organização, mas não estão atribuídos a um usuário ou um telefone. Para lidar com essas chamadas, configure uma tabela de números não atribuídos. Você pode usar a tabela para rotear as chamadas para um aplicativo de anúncio ou para um servidor de UM do Exchange.
  
O modo como você configura a tabela de números não atribuída depende de como você deseja usá-la. É possível configurar a tabela com todas as extensões válidas para sua organização, com apenas extensões não atribuídas ou com uma combinação de ambos os tipos de números. A tabela de números não atribuída pode incluir números atribuídos e não atribuídos, mas é chamada somente quando um chamador disca um número que não está atribuído no momento. Se você incluir todas as extensões válidas na tabela de números não atribuída, você poderá especificar a ação que ocorre sempre que alguém deixa sua organização, sem a necessidade de reconfigurar a tabela. Se você incluir extensões não atribuídas na tabela, poderá personalizar a ação que ocorre para números específicos. Por exemplo, se você alterar a extensão para seu atendimento ao cliente, poderá incluir o número antigo de atendimento ao cliente na tabela, e atribuí-lo a um anúncio que fornece o novo número.
  
## <a name="configure-unassigned-phone-numbers"></a>Configurar números de telefone não atribuídos

Use um dos seguintes procedimentos para configurar intervalos de números não atribuídos para o aplicativo de anúncio.
  
> [!IMPORTANT]
> Antes de configurar a tabela de números não atribuída, seu sistema deve já ativa anúncios definidos ou um atendedor automático de Exchange Unified Messaging (UM) configurado. 
  
> [!TIP]
> Quando alguém chama um número não atribuído, Skype para Business Server procura na tabela de número não atribuída de cima para baixo e usa o primeiro intervalo correspondente. Portanto, uma ação que você deseja executar como última alternativa deve ser especificada para o último intervalo na tabela. 
  
### <a name="to-use-skype-for-business-server-control-panel-to-configure-unassigned-phone-numbers"></a>Para usar o Skype para painel de controle do Business Server para configurar números telefônicos não atribuídos

1. Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como um membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte **Delegate Setup Permissions**.
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.  
    
3. Na barra de navegação à esquerda, clique em **Recursos de Voz** e depois, em **Número Não Atribuído**.
    
4. Na página **Números não atribuídos**, siga um destes procedimentos:
    
   - Para criar um novo intervalo de números, clique em **Novo**. Em **Nome**, digite o nome que identifica este intervalo de números.
    
     > [!NOTE]
     > Depois de confirmar o novo intervalo de números não atribuídos para o banco de dados, não é possível alterar este nome. 
  
   - Para modificar um intervalo de números existente, digite todo o nome do intervalo de órbita, ou parte dele, no campo de pesquisa. Na lista de resultados de intervalos de número, clique no nome desejado, clique em **Editar** e depois, clique em **Exibir Detalhes**.
    
5. No primeiro campo **Intervalo Numérico**, digite o número inicial do intervalo e no segundo campo **Intervalo Numérico** digite o número final do intervalo.
    
   - O número inicial do intervalo deve ser menor ou igual ao número final.
    
   - Se o número inicial ou o número final do intervalo incluir um número de ramal, ambos os números devem incluir um ramal, que deve ser o mesmo para ambos.
    
   - Os números devem corresponder à expressão regular (tel:) ? (\+) ? [1-9] \d{0,17}(; ext = [1-9] \d{0,9}) ?. Isso significa que o número pode começar com o cadeia de caracteres tel: (se você não especificar essa cadeia de caracteres, ele será automaticamente adicionado para você), um sinal de adição (+) e um dígito entre 1 e 9. O número de telefone pode ter até 17 dígitos e pode ser seguido de um ramal no formato ;ext= seguido do número do ramal.
    
6. Em **Serviço de Comunicado**, execute um dos seguintes procedimentos: 
    
   - Clique em **Comunicado**.
    
   - Clique em **UM do Exchange**.
    
7. Se, na etapa anterior, você clicou em **Comunicado**, execute:
    
    a. Em **FQDN do servidor de destino**, clique em **Selecionar**, clique na ID de serviço do serviço aplicativo que executa o aplicativo de comunicado que irá lidar com chamadas de entrada para esse intervalo de números não atribuídos e clique em **Okey**.
    
    b. Em **Comunicado**, clique no comunicado a ser reproduzido para este intervalo de números não atribuídos.
    
8. Se, na etapa anterior, você clicou em **UM do Exchange**, sob **Número de telefone do Atendedor Automático**, clique em **Selecionar**, clique no número de telefone a ser usado para este intervalo de números não atribuídos e clique em **OK**.
    
9. Clique em **OK**.
    
10. Na página **Número Não Atribuído**, certifique-se de que os intervalos numéricos não atribuídos estejam organizados da ordem que você deseja. Para alterar a posição do intervalo na tabela, clique em um ou mais nomes consecutivos na lista de intervalos e clique na seta para cima ou para baixo.
    
    > [!TIP]
    > Skype para Business Server procura na tabela de número não atribuída de cima para baixo e usa o primeiro intervalo que corresponde ao número não atribuído. Se você tem intervalos sobrepostos e um intervalo que especifica uma última ação de reclassificação, certifique-se de que o intervalo esteja no final da lista. 
  
11. Quando os intervalos numéricos não atribuídos estiverem na ordem desejada, clique em **Confirmar tudo**.
    
### <a name="to-use-skype-for-business-server-management-shell-to-configure-unassigned-phone-numbers"></a>Para usar o Skype para Business Server Management Shell para configurar números telefônicos não atribuídos

1. Faça logon no computador onde o Skype do Shell de gerenciamento do servidor de negócios está instalado como membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário necessários, conforme descrito em **Delegate Setup Permissions**.
    
2. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
3. Use **New-CsUnassignedNumber** para criar um intervalo de números não atribuídos. Use **Set-CsUnassignedNumber** para modificar um intervalo de números não atribuídos existente.
    
    > [!TIP]
    > Se você tiver intervalos sobrepostos e desejar que os intervalos sejam aplicados em uma ordem específica, inclua o parâmetro Prioridade. O intervalo com a maior prioridade será aplicado à chamada. O valor 0 representa a prioridade mais alta.
  
    No linha de comando, siga um destes procedimentos:
    
   - Para criar um intervalo numérico para um serviço de Comunicado, execute:
    
     ```
     New-CsUnassignedNumber -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -AnnouncementName <announcement name> -AnnouncementService <FQDN or service ID of the Announcement service>
     ```

   - Ou para criar um intervalo numérico para Atendedor Automático do UM do Exchange, execute:
    
     ```
     New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber <phone number> -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range>
     ```

     Por exemplo:
    
     ```
     New-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100" -AnnouncementName "Welcome Announcement" -AnnouncementService ApplicationServer:Redmond.contoso.com
     ```

     Ou
    
     ```
     New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber "+12065551234" -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100"
     ```

     O exemplo a seguir mostra como modificar os números em um intervalo numérico não atribuído existente.
    
     ```
     Set-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551900"
     ```

## <a name="delete-an-unnasigned-number-range"></a>Excluir um intervalo de números não atribuídos

### <a name="to-use-skype-for-business-server-control-panel-to-delete-an-unassigned-number-range"></a>Para usar o Skype para painel de controle do Business Server para excluir um intervalo de números não atribuído

1.  Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como um membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte **Delegate Setup Permissions**.
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.  
    
3. Na barra de navegação à esquerda, clique em **Recursos de Voz** e depois, em **Número Não Atribuído**.
    
4. Na página **Número Não Atribuído**, no campo de pesquisa, digite todo ou parte do nome do intervalo numérico não atribuído que deseja excluir.
    
5. Na lista de resultados de intervalos de número, clique no nome, clique em **Editar** e depois, clique em **Excluir**.
    
6. Clique em **Confirmar tudo**.
    
### <a name="to-use-skype-for-business-server-management-shell-to-delete-an-unassigned-number-range"></a>Para usar o Skype para Business Server Management Shell para excluir um intervalo de números não atribuído

1. Faça logon no computador onde o Skype do Shell de gerenciamento do servidor de negócios está instalado como membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário necessários, conforme descrito em **Delegate Setup Permissions**.
    
2. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
3. Na linha de comando, digite:
    
   ```
   Remove-CsUnassignedNumber -Identity "<name of unassigned number range>" 
   ```

    Por exemplo:
    
   ```
   Remove-CsUnassignedNumber -Identity "Unassigned range 1"
   ```

    > [!NOTE]
    > Para obter detalhes sobre mais opções, consulte [Remove-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/remove-cscallparkorbit?view=skype-ps). 
  
## <a name="see-also"></a>Consulte Também

[New-CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/new-csunassignednumber?view=skype-ps)
  
[Set-CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/set-csunassignednumber?view=skype-ps)
  
[Get-CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/get-csunassignednumber?view=skype-ps)
