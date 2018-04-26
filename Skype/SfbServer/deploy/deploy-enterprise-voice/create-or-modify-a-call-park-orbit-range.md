---
title: Criar ou modificar um intervalo de Órbita do Call Park no Skype for Business 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 549ec118-eee5-4333-9416-80929ec057e0
description: Criar ou modificar um intervalo de Órbita do Call Park no Skype for Business 2015
ms.openlocfilehash: 3617fb739d56e395c31359c6cedae74e9fb63756
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="create-or-modify-a-call-park-orbit-range-in-skype-for-business-2015"></a>Criar ou modificar um intervalo de Órbita do Call Park no Skype for Business 2015
 
Criar ou modificar um intervalo de Órbita do Call Park no Skype for Business 2015
  
Call Park uses orbits for parking calls. Before users can park and retrieve calls, you must configure the Call Park orbit table. You need to specify the ranges of extension numbers (orbits) that your organization will reserve for parking calls and define the routing for those ranges by specifying which Call Park pool handles each range. When you define orbit ranges, the goal is to have enough orbits so that any one orbit is not reused too quickly, but not so many orbits that you limit the number of extensions available for users or other services. You can create multiple Call Park orbit ranges for each Skype for Business Server pool where the Call Park application is deployed. Each Call Park orbit range must have a globally unique name and a unique set of extensions.
  
> [!IMPORTANT]
> Normalmente, um intervalo de órbitas engloba 100 órbitas ou menos. Cada intervalo pode ser muito maior, contanto que seja menor do que o máximo de 10.000 órbitas por intervalo e tenha menos de 50.000 órbitas por pool. Se o intervalo for muito pequeno, as órbitas serão reutilizadas mais rapidamente. 
  
Use blocos de extensões virtuais (extensões sem um usuário ou telefone atribuído a elas) para intervalos de órbita. 
  
> [!NOTE]
> Não há suporte para a atribuição dos números DID (Discagem Direta de Entrada) como números de órbita na tabela de órbita de estacionamento de chamada. 
  
Utilize um dos seguintes procedimentos para criar ou modificar um intervalo de órbitas de estacionamento de chamada. 
  
### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a>Para usar o  para criar ou modificar um novo intervalo numérico para o estacionamento de chamada

1. Efetue logon no computador como membro do grupo RTCUniversalServerAdmins ou como membro da função Cs-VoiceAdministrator, Cs-ServerAdministratorou CsAdministrator. For details, see **Delegate Setup Permissions**.
    
2. Você também pode abrir uma janela do navegador e inserir a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.  
    
3. Na barra de navegação esquerda, clique em **Recursos de Voz** e em **Estacionamento de Chamada(Call Park)**.
    
4. Na página **Estacionamento de Chamada**, execute um dos seguintes procedimentos:
    
  - Para criar um novo intervalo de órbitas, clique em **Novo**. Em **Nome**, digite um nome de identificação para esse intervalo de números.
    
    > [!NOTE]
    > Após confirmar o intervalo de órbitas do banco de dados, não será possível alterar esse nome. 
  
  - Para modificar um intervalo de órbitas existente, digite todo ou parte do nome do intervalo de órbitas no campo de pesquisa. Na lista de resultados de órbitas, clique na órbita que desejar, clique em **Editar** e clique em **Mostrar detalhes**.
    
5. No primeiro campo do **Intervalo numérico**, digite o número inicial do intervalo de extensões desta órbita de estacionamento de chamada e, no segundo campo **Intervalo numérico**, digite o número final do intervalo. Be aware:
    
   - O número inicial do intervalo deve ser menor ou igual ao número final.
    
   - O valor do número inicial do intervalo deve ter o mesmo comprimento que o número final do intervalo.
    
   - O intervalo de órbita deve ser exclusivo. Este intervalo não pode sobrepor outro intervalo.
    
   - Se o intervalo de órbita começa com o caractere * ou #, o intervalo deve ser maior que 100.
    
   - Valores válidos: Deve corresponder a cadeia de caracteres de expressão regular ([\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}). Isto significa que o valor deve ser uma cadeia de caracteres começando com o caractere * ou # ou um número de 1 a 9 (o primeiro caractere não pode ser zero). Se o primeiro caractere é * ou #, o seguinte caractere deve ser um número de 1 a 9 (não pode ser zero). Os caracteres subsequentes podem ser qualquer número de 0 a 9 até sete caracteres adicionais (por exemplo, "#6000", "*92000", "*95551212" e "915551212"). Se o primeiro caractere não é * ou #, deve ser um número de 1 a 9 (não pode ser zero), seguido por oito caracteres, cada um com número de 0 a 9 (por exemplo: "915551212", "41212", "300").
    
   - Você não deve ter mais do que um total de 50.000 órbitas por pool. Cada intervalo de órbita geralmente possui 100 ou menos órbitas, mas pode ser muito maior contanto que inclua menos do que 10.000 órbitas. Por exemplo, ao invés de especificar um número inicial de "7000000" e um número final de "8000000," considere especificar um número inicial de "7000000" e um número final de "7000100."
    
6. No FQDN do servidor de destino, clique no nome de domínio totalmente qualificado (FQDN) ou ID de serviço do serviço do aplicativo que hospeda o . Todas as chamadas estacionadas em números dentro do intervalo especificado pelo número inicial e número final do intervalo de órbita serão direcionadas para este servidor ou pool.
    
7. Clique em **Confirmar**.
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a>Para usar o  para criar ou modificar um novo intervalo numérico para o estacionamento de chamada

1. Faça logon no computador onde o  está instalado como um membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário necessários, conforme descrito em .
    
2. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
3. Use o **** para criar um novo intervalo de números de órbitas. Use o **** para modificar um intervalo de números de órbitas de estacionamento de chamada existente.
    
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

#### 

[New-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/new-cscallparkorbit?view=skype-ps)
  
[Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/set-cscallparkorbit?view=skype-ps)
  
[Delete a Call Park Orbit Range](http://technet.microsoft.com/library/85e9f916-062d-450d-ac0a-aeaefc0f7cdc.aspx)

