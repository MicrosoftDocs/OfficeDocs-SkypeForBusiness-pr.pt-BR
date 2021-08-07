---
title: Configurar uma conta de recurso no Skype for Business Server 2019
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: wasseemh
ms.audience: ITPro
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Configurar uma conta de recurso para Skype for Business Server 2019.
ms.openlocfilehash: 87db9779a6f90730d6aa53e3084a2014a71bad5aba91844d2e545f7d78ae37cf
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54304693"
---
# <a name="configure-resource-accounts"></a>Configurar contas de recurso

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Skype for Business Server implementações híbridas de 2019 usam apenas serviços de nuvem fornecidos pelo Sistema de Telefonia para unificação de mensagens e não se integram ao Exchange Online. No Skype for Business Server 2019, agora você pode usar as filas de chamada na nuvem e os atendimentos automáticos descritos em Aqui está o que você obter com o Sistema de Telefonia em Microsoft 365 ou [Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system).

Para usar um atendente automático ou fila de chamadas do Sistema de Telefonia com o Skype for Business Server 2019, você precisará criar contas de recurso que atuam como pontos de extremidade do aplicativo e podem ser atribuídas a números de telefone e, em seguida, usar o centro de administração do Teams online para configurar a fila de chamadas ou o atendimento automático. Essa conta de recurso pode ser homed online (consulte [Gerenciar](/MicrosoftTeams/manage-resource-accounts) contas de recursos no Microsoft Teams para criar contas de recursos em casa online) ou no local, conforme descrito neste artigo. Normalmente, você terá vários nós de Sistema de Telefonia automático ou fila de chamada, cada um deles mapeado para contas de recurso, que podem ser ativas online ou em Skype for Business Server 2019.

Se você tiver um sistema de filas de chamada e atendimento automático de um Exchange existente, antes de alternar para o Exchange Server 2019 ou o Exchange online, será necessário registrar manualmente os detalhes conforme descrito abaixo e implementar um sistema completamente novo usando o centro de administração Teams.

## <a name="overview"></a>Visão Geral

Se o Sistema de Telefonia ou fila de chamada precisar de um número de serviço, as várias dependências poderão ser atendidas na seguinte sequência:

1. Obtenha um número de serviço.
2. Obtenha uma licença Sistema de Telefonia de usuário [virtual](/MicrosoftTeams/teams-add-on-licensing/virtual-user) ou uma licença de Sistema de Telefonia paga para usar com a conta de recurso.
3. Crie a conta de recurso. Um atendimento automático ou fila de chamada é necessário para ter uma conta de recurso associada.
4. Aguarde uma sincronização do active directory entre online e local.
5. Atribua a Sistema de Telefonia de usuário à conta de recurso.
6. Atribua um número de serviço à conta de recurso.
7. Crie uma fila Sistema de Telefonia de chamada ou atendimento automático.
8. Associe a conta de recurso a um atendimento automático ou fila de chamada: (New-CsApplicationInstanceAssociation).

Se o atendimento automático ou fila de chamadas estiver aninhado em um atendimento automático de nível superior, a conta de recurso associada só precisará de um número de telefone se você quiser vários pontos de entrada na estrutura de atendimentos automáticos e filas de chamadas.

Para redirecionar chamadas para pessoas em sua organização que  estão habilitadas online, elas devem ter uma licença de Sistema de Telefonia e estar habilitadas para o Enterprise Voice ou ter planos Microsoft 365 ou Office 365 chamadas. Consulte [Atribuir Microsoft Teams licenças](/MicrosoftTeams/assign-teams-licenses). Para habilita-Enterprise Voice, você pode usar Windows PowerShell. Por exemplo, execute:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

Se o Telefone do sistema ou a fila de chamadas que você estiver criando serão aninhados e não precisarão de um número de telefone, o processo será:

1. Criar a conta de recurso  
2. Aguarde uma sincronização do active directory entre online e local
3. Criar um Sistema de Telefonia automático ou fila de chamada
4. Associar a conta de recurso a um Sistema de Telefonia automático ou fila de chamada

## <a name="create-a-resource-account-with-a-phone-number"></a>Criar uma conta de recurso com um número de telefone

A criação de uma conta de recurso que usa um número de telefone exigiria a execução das seguintes tarefas na seguinte ordem:

1. Port or get a toll or toll-free service number. O número não pode ser atribuído a nenhum outro serviço de voz ou contas de recurso.

   Antes de atribuir um número de telefone a uma conta de recurso, você precisará obter ou portuar seus números de serviço de chamada gratuita ou de chamada gratuita existentes. Depois que você receber os números de telefone de chamada gratuita ou de chamada gratuita, eles aparecerão no centro de administração Microsoft Teams Números de voz Telefone voz e o tipo de número listado será listado como  >    >   **Serviço -**  Gratuito . Para obter seus números de serviço, consulte [Obter](/MicrosoftTeams/getting-service-phone-numbers) números de telefone de serviço ou se você deseja transferir um número de serviço existente, consulte [Transfer phone numbers to Teams](/MicrosoftTeams/phone-number-calling-plans/transfer-phone-numbers-to-teams).

   Se você estiver fora dos Estados Unidos, não poderá usar o centro de administração Microsoft Teams para obter números de serviço. Vá para [Gerenciar números de telefone para sua organização,](/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization) em vez disso, para ver como fazê-lo de fora dos Estados Unidos.

2. Compre uma Sistema de Telefonia de compra. Confira:  
   - [Sistema de Telefonia–licença de usuário virtual](/MicrosoftTeams/teams-add-on-licensing/virtual-user)
   - [Office 365 Enterprise E1 e E3](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e1-e3)
   - [Office 365 Enterprise E5](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e5-with-audio-conferencing)
   - [Office 365 Enterprise E5 Business Software](https://products.office.com/business/office-365-enterprise-e5-business-software)

3. Crie uma conta de recurso local executando o cmdlet para cada Sistema de Telefonia automático ou fila de chamada e dê a cada um nome, endereço sip e assim `New-CsHybridApplicationEndpoint` por diante.

    ``` Powershell
    New-CsHybridApplicationEndpoint -ApplicationID <GUID> -DisplayName appinstance01 -SipAddress sip:appinstance01@contoso.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    Consulte [New-CsHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) para obter mais detalhes sobre este comando.

4. (Opcional) Depois que suas contas de recurso são criadas, você pode aguardar que o AD sincronize entre o local e online ou forçar uma sincronização e prosseguir para a configuração online do Sistema de Telefonia automático ou filas de chamada. Para forçar uma sincronização, você executaria o seguinte comando no computador que executa o AAD Conexão (se você ainda não fez isso, precisaria carregar para executar `import-module adsync` o comando):

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    Consulte [Start-ADSyncSyncCycle](/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) para obter mais detalhes sobre este comando.
    
    Observação Neste ponto, a conta pode ter sido sincronizada, mas o provisionamento pode não estar concluído.  Verifique a saída de [Get-CsOnlineApplicationEndpoint](/powershell/module/skype/get-csonlineapplicationendpoint).  Se o ponto de extremidade sincronizado ainda não tiver concluído o provisionamento, ele não aparecerá aqui.  Você pode verificar o status das solicitações de provisionamento no portal M365 em Teams [Status da Instalação.](https://admin.microsoft.com/AdminPortal/Home#/teamsprovisioning)  Essa fase de provisionamento pode levar até 24 horas.

5. Atribua a Sistema de Telefonia - Usuário Virtual ou Sistema de Telefonia à conta de recurso. Consulte [Atribuir Microsoft Teams licenças de complemento e](/MicrosoftTeams/teams-add-on-licensing/assign-teams-add-on-licenses) Atribuir [licenças aos usuários.](/microsoft-365/admin/manage/assign-licenses-to-users)

   Se você estiver atribuindo um número de telefone a uma conta de recurso, agora poderá usar a licença de Sistema de Telefonia - Usuário Virtual. Isso fornece Sistema de Telefonia recursos para números de telefone no nível organizacional e permite que você crie recursos de atendimento automático e fila de chamadas.


6. Atribua o número de serviço à conta de recurso. Use o `Set-CsHybridApplicationEndpoint` comando para atribuir um número de telefone (com a opção -LineURI) à conta de recurso.

    ``` Powershell
    Set-CsHybridApplicationEndpoint -Identity appinstance01@contoso.com -LineURI tel:+14255550100
    ```

    Consulte [Set-CsHybridApplicationEndpoint](/powershell/module/skype/set-cshybridapplicationendpoint?view=skype-ps) para obter mais detalhes sobre este comando.

    Para atribuir um roteamento direto ou número híbrido a uma conta de recurso, use o seguinte cmdlet:

   ``` Powershell
   Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
   ```

   A conta de recurso precisará de um número de telefone atribuído se ela for atribuída a um atendente automático de nível superior ou fila de chamadas. Os números de telefone de usuário (assinante) não podem ser atribuídos a uma conta de recurso, apenas números de telefone de chamada gratuita ou de chamada gratuita podem ser usados.

     Você pode atribuir um roteamento direto ou número híbrido à sua conta de recurso. Para obter detalhes, consulte [Plan Direct Routing and](/MicrosoftTeams/direct-routing-plan) Plan Cloud auto [attendants](plan-cloud-auto-attendant.md).

     > [!NOTE]
     > Os números de serviço de Roteamento Direto atribuídos a contas de recursos para filas de chamadas e atendimento automático são suportados somente para Microsoft Teams usuários e agentes.

7. Crie o Sistema de Telefonia ou fila de chamada automática. Confira um dos procedimentos a seguir:

   - [Configurar um atendedor automático do Cloud](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [Criar uma fila de chamada do Cloud](/MicrosoftTeams/create-a-phone-system-call-queue)  

8. Associe a conta de recurso ao Sistema de Telefonia ou fila de chamada escolhida anteriormente.

## <a name="create-a-resource-account-without-a-phone-number"></a>Criar uma conta de recurso sem um número de telefone

Esta seção discute a criação de uma conta de recurso que está em casa no local. A criação de uma conta de recurso que está em casa online é discutida em Gerenciar contas [de recursos em Microsoft Teams](/MicrosoftTeams/manage-resource-accounts).

Essas etapas são necessárias se você está criando um novo Sistema de Telefonia de atendimento automático ou estrutura de fila de chamada ou a reconstrução da estrutura originalmente criada na UM Exchange.

Faça logon no servidor Skype for Business front-end e execute os seguintes cmdlets do PowerShell:

1. Crie uma conta de recurso local executando o cmdlet para cada Sistema de Telefonia automático ou fila de chamada e dê a cada um nome, endereço sip e assim `New-CsHybridApplicationEndpoint` por diante.

    ``` Powershell
    New-CsHybridApplicationEndpoint -DisplayName appinstance01 -SipAddress sip:appinstance01@litwareinc.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    Consulte [New-CsHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) para obter mais detalhes sobre este comando.

2. (Opcional) Depois que suas contas de recurso são criadas, você pode aguardar que o AD sincronize entre o local e online ou forçar uma sincronização e prosseguir para a configuração online do Sistema de Telefonia automático ou filas de chamada. Para forçar uma sincronização, você executaria o seguinte comando no computador que executa o AAD Conexão (se você ainda não fez isso, precisaria carregar para executar `import-module adsync` o comando):

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    Consulte [Start-ADSyncSyncCycle](/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) para obter mais detalhes sobre este comando.

3. Crie o Sistema de Telefonia ou fila de chamada automática. Confira um dos procedimentos a seguir:
   - [Configurar um atendedor automático do Cloud](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [Criar uma fila de chamada do Cloud](/MicrosoftTeams/create-a-phone-system-call-queue)  
4. Associe a conta de recurso e o Sistema de Telefonia ou fila de chamada escolhida anteriormente.

## <a name="test-the-implementation"></a>Testar a implementação

A melhor maneira de testar a implementação é chamar o número configurado para um Sistema de Telefonia ou fila de chamada automática e conectar-se a um dos agentes ou menus. Você também pode fazer uma chamada de teste rapidamente usando o botão **Testar** no painel Ação do centro de administração. Se você quiser fazer alterações em um Sistema de Telefonia automático ou fila de chamada, selecione-o e, no painel Ação, clique em **Editar**. 

> [!TIP]
> Se [sua](/MicrosoftTeams/Known-issues#phone-system) conta de recurso tiver dificuldades para ser atribuída a uma fila de chamada ou a um atendimento automático, consulte Problemas conhecidos para Microsoft Teams e a seção Como corrigir minhas [instâncias](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521) de aplicativo híbrido no blog do Microsoft Teams.

## <a name="moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system"></a>Mover um Exchange de chamada ou atendimento automático de UM para Sistema de Telefonia

A migração Exchange UM para Sistema de Telefonia exigirá recriar a fila de chamada e a estrutura do atendimento automático, não há suporte para migração direta de uma para a outra. Para implementar um conjunto de filas de chamada e atendimentos automáticos:

1. Obter uma lista de todos os Exchange de chamada e filas de chamada da UM executando o seguinte comando no sistema Exchange 2013 ou 2016 enquanto estiver conectado como administrador:

    ``` Powershell
    Get-UMAutoAttendant | Format-List
    ```

2. Para cada fila de chamada de UM listada ou atendimento automático, observe seu lugar na estrutura, configurações e obter cópias de arquivos de som ou texto para fala associados (o guid na saída será o nome de uma pasta onde os arquivos estão armazenados). Exchange Você pode obter esses detalhes executando o comando:

    ``` Powershell
    Get-UMAutoAttendant -Identity MyUMAutoAttendant
    ```

    Consulte [Get-UMAutoAttendant para](/powershell/module/exchange/unified-messaging/get-umautoattendant?view=exchange-ps) obter mais detalhes sobre este comando. Uma lista completa de opções que você pode precisar capturar está nos membros [umAutoAttendant,](/previous-versions/office/exchange-server-api/ff340649(v=exchg.150)) mas as opções mais importantes a observar para baixo são:

    - Horário comercial
    - Horário não comercial
    - Idioma
    - Agendamento de Feriado

3. Crie novos pontos de extremidade locais conforme descrito anteriormente.
   Atribua ao atendimento automático de nível superior um número temporário para fins de teste.

4. Configure um Sistema de Telefonia ou fila de chamada automática que usa os pontos de extremidade conforme descrito anteriormente.

5. Teste o Sistema de Telefonia ou fila de chamada automática.

6. Reatribua o número de telefone vinculado à fila Exchange chamada da UM ou ao atendimento automático correspondente Sistema de Telefonia ou fila de chamada.  

   Neste ponto, se você já tiver migrado a Caixa Postal da UM, deverá estar em posição de migrar para o Exchange Server 2019.

## <a name="see-also"></a>Confira também

[Criar uma fila de chamada do Cloud](/MicrosoftTeams/create-a-phone-system-call-queue)

[Quais são os atendedores automáticos do Cloud?](/MicrosoftTeams/what-are-phone-system-auto-attendants)

[Configurar um atendedor automático do Cloud](/MicrosoftTeams/create-a-phone-system-auto-attendant)  

[Atendedores automáticos do plano da nuvem](plan-cloud-auto-attendant.md)

[Planejar filas de chamadas da nuvem](plan-call-queue.md)

[Planejar Caixa postal na Nuvem serviço para usuários locais](plan-cloud-voicemail.md)

[New-CsHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[New-CsOnlineApplicationInstance](/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

[Gerenciar contas de recursos em Microsoft Teams](/MicrosoftTeams/manage-resource-accounts)  -  \( para criar contas de recursos em casa online\)