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
description: Configurar uma conta de recurso para o Skype for Business Server 2019.
ms.openlocfilehash: 1d8294eb717982b5ac68df06a5370059e83a62c5
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2021
ms.locfileid: "49919007"
---
# <a name="configure-resource-accounts"></a>Configurar contas de recurso

As implementações híbridas do Skype for Business Server 2019 usam apenas serviços de nuvem fornecidos pelo Sistema de Telefonia para unificação de mensagens e não se integram ao Exchange Online. No Skype for Business Server 2019, agora você pode usar as filas de chamadas na nuvem e os atendentes automáticos descritos em Aqui está o que você recebe com o Sistema de Telefonia no [Microsoft 365 ou Office 365.](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

Para usar um atendente automático do Sistema de Telefonia ou uma fila de chamadas com o Skype for Business Server 2019, você precisará criar contas de recursos que atuam como pontos de extremidade do aplicativo e podem receber números de telefone e, em seguida, usar o centro de administração do Teams online para configurar a fila de chamadas ou o atendente automático. Essa conta de recurso pode ser usada online (confira Gerenciar contas de recursos no [Microsoft Teams](/MicrosoftTeams/manage-resource-accounts) para criar contas de recursos que estão online) ou no local, conforme descrito neste artigo. Normalmente, você terá vários nós de fila de chamadas ou de atendimento automático do Sistema de Telefonia, cada um deles mapeado para contas de recursos, que podem ser ativas online ou no Skype for Business Server 2019.

Se você tiver um servidor automático de UM do Exchange e um sistema de fila de chamada, antes de mudar para o Exchange Server 2019 ou Exchange Online, será necessário registrar manualmente os detalhes conforme descrito abaixo e implementar um sistema completamente novo usando o centro de administração do Teams.

## <a name="overview"></a>Visão geral

Se o seu atendente automático ou fila de chamadas do Sistema de Telefonia precisar de um número de serviço, as várias dependências poderão ser atendidas na seguinte sequência:

1. Obtenha um número de serviço.
2. Obtenha um Sistema de Telefonia gratuito - [licença de Usuário Virtual](/MicrosoftTeams/teams-add-on-licensing/virtual-user) ou uma licença paga do Sistema de Telefonia para usar com a conta de recurso.
3. Crie a conta de recurso. Um atendente automático ou fila de chamada é necessário para ter uma conta de recurso associada.
4. Aguarde uma sincronização do Active Directory entre online e local.
5. Atribua a licença do Sistema de Telefonia à conta de recurso.
6. Atribua um número de serviço à conta de recurso.
7. Crie uma fila de chamadas do Sistema de Telefonia ou um atendente automático.
8. Associe a conta de recurso a um atendente automático ou fila de chamada: (New-CsApplicationInstanceAssociation).

Se o atendente automático ou a fila de chamadas estiver aninhada em um atendente automático de nível superior, a conta de recurso associada só precisará de um número de telefone se você quiser vários pontos de entrada na estrutura de atendentes automáticos e filas de chamadas.

Para redirecionar chamadas para pessoas em sua organização que  estão habilitadas online, elas devem ter uma licença do Sistema de Telefonia e estar habilitadas para o Enterprise Voice ou ter Planos de Chamadas do Microsoft 365 ou Office 365. Confira [Atribuir licenças do Microsoft Teams.](/MicrosoftTeams/assign-teams-licenses) Para habilita-los para o Enterprise Voice, você pode usar o Windows PowerShell. Por exemplo, execute:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

Se o atendente automático do sistema de telefonia ou a fila de chamadas que você está criando for aninhado e não precisar de um número de telefone, o processo será:

1. Criar a conta de recurso  
2. Aguardar uma sincronização do Active Directory entre online e local
3. Criar um atendente automático ou fila de chamadas do Sistema de Telefonia
4. Associar a conta de recurso a um atendente automático ou fila de chamadas do Sistema de Telefonia

## <a name="create-a-resource-account-with-a-phone-number"></a>Criar uma conta de recurso com um número de telefone

Criar uma conta de recurso que use um número de telefone exigiria a execução das seguintes tarefas na seguinte ordem:

1. Fazer a portabilidade ou obter um número de serviço gratuito ou gratuito. O número não pode ser atribuído a outros serviços de voz ou contas de recursos.

   Antes de atribuir um número de telefone a uma conta de recurso, você precisará obter ou fazer a portabilidade de seus números de serviço de chamada tarifada ou gratuita existentes. Depois que você receber os números de telefone de serviço de chamada tarifada ou gratuita, eles aparecerão nos números de telefone de voz do centro de administração do **Microsoft Teams,** e o tipo de número listado será listado como Serviço  >    >   **-** Gratuito.  Para obter seus números [](/MicrosoftTeams/getting-service-phone-numbers) de serviço, consulte Obter números de telefone de serviço ou se deseja transferir um número de serviço existente, confira Transferir números de telefone [para o Teams.](/MicrosoftTeams/phone-number-calling-plans/transfer-phone-numbers-to-teams)

   Se você estiver fora dos Estados Unidos, não poderá usar o centro de administração do Microsoft Teams para obter números de serviço. Vá para [Gerenciar números de telefone da sua organização](/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization) para ver como fazer isso fora dos Estados Unidos.

2. Compre uma licença do Sistema de Telefonia. Confira:  
   - [Sistema de Telefonia – Licença de Usuário Virtual](/MicrosoftTeams/teams-add-on-licensing/virtual-user)
   - [Office 365 Enterprise E1 e E3](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e1-e3)
   - [Office 365 Enterprise E5](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e5-with-audio-conferencing)
   - [Office 365 Enterprise E5 Business Software](https://products.office.com/business/office-365-enterprise-e5-business-software)

3. Crie uma conta de recurso local executando o cmdlet para cada fila de chamadas ou atendimento automático do Sistema de Telefonia e dê a cada um deles um nome, endereço sip e assim `New-CsHybridApplicationEndpoint` por diante.

    ``` Powershell
    New-CsHybridApplicationEndpoint -ApplicationID <GUID> -DisplayName appinstance01 -SipAddress sip:appinstance01@contoso.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    Consulte [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) para obter mais detalhes sobre este comando.

4. (Opcional) Depois que suas contas de recursos são criadas, você pode esperar que o AD seja sincronizado entre online e local ou forçar uma sincronização e prosseguir com a configuração online do atendente automático do Sistema de Telefonia ou filas de chamadas. Para forçar uma sincronização, execute o seguinte comando no computador que executa o AAD Connect (se ainda não tiver feito isso, será necessário carregar para executar `import-module adsync` o comando):

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    Consulte [Start-ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) para obter mais detalhes sobre esse comando.
    
    Note-at this point, the account may have synced, but provisioning may not be complete.  Verifique a saída de [Get-CsOnlineApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/get-csonlineapplicationendpoint).  Se o ponto de extremidade sincronizado ainda não tiver concluído o provisionamento, ele não aparecerá aqui.  Você pode verificar o status das solicitações de provisionamento no portal do M365 em [Status de Instalação do Teams.](https://admin.microsoft.com/AdminPortal/Home#/teamsprovisioning)  Essa fase de provisionamento pode levar até 24 horas.

5. Atribua a licença do Sistema de Telefonia - Usuário Virtual ou Sistema de Telefonia à conta de recurso. Confira [Atribuir licenças de complemento do Microsoft Teams](/MicrosoftTeams/teams-add-on-licensing/assign-teams-add-on-licenses) e atribuir [licenças aos usuários.](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)

   Se você estiver atribuindo um número de telefone a uma conta de recurso, agora poderá usar a licença sistema de telefonia gratuita - Usuário Virtual. Isso fornece recursos do Sistema de Telefonia para números de telefone no nível organizacional e permite que você crie recursos de atendimento automático e fila de chamadas.


6. Atribua o número de serviço à conta de recurso. Use o `Set-CsHybridApplicationEndpoint` comando para atribuir um número de telefone (com a opção -LineURI) à conta de recurso.

    ``` Powershell
    Set-CsHybridApplicationEndpoint -Identity appinstance01@contoso.com -LineURI tel:+14255550100
    ```

    Consulte [Set-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/set-cshybridapplicationendpoint?view=skype-ps) para obter mais detalhes sobre este comando.

    Para atribuir um Roteamento Direto ou um número híbrido a uma conta de recurso, use o seguinte cmdlet:

   ``` Powershell
   Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
   ```

   A conta de recurso precisará de um número de telefone atribuído se ele for atribuído a um atendente automático de nível superior ou fila de chamadas. Os números de telefone do usuário (assinante) não podem ser atribuídos a uma conta de recurso, apenas números de telefone de chamada tarifada ou gratuita podem ser usados.

     Você pode atribuir um Roteamento Direto ou um número híbrido à sua conta de recurso. Para obter detalhes, consulte [Plan Direct Routing](/MicrosoftTeams/direct-routing-plan) and Plan Cloud auto [attendants](plan-cloud-auto-attendant.md).

     > [!NOTE]
     > Os números de serviço de Roteamento Direto atribuídos a contas de recursos para o atendente automático e as filas de chamadas são suportados apenas para usuários e agentes do Microsoft Teams.

7. Crie o atendente automático ou fila de chamadas do Sistema de Telefonia. Confira um dos procedimentos a seguir:

   - [Configurar um atendedor automático do Cloud](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [Criar uma fila de chamada do Cloud](/MicrosoftTeams/create-a-phone-system-call-queue)  

8. Associe a conta de recurso ao atendente automático ou fila de chamadas do Sistema de Telefonia escolhido anteriormente.

## <a name="create-a-resource-account-without-a-phone-number"></a>Criar uma conta de recurso sem um número de telefone

Esta seção discute a criação de uma conta de recurso que é homed no local. A criação de uma conta de recurso que está online é discutida em [Gerenciar contas de recursos no Microsoft Teams.](/MicrosoftTeams/manage-resource-accounts)

Essas etapas são necessárias, independentemente de você estar criando um novo atendente automático do Sistema de Telefonia ou uma estrutura de fila de chamadas ou recomando a estrutura originalmente criada na UM do Exchange.

Faça logon no servidor front-end do Skype for Business e execute os seguintes cmdlets do PowerShell:

1. Crie uma conta de recurso local executando o cmdlet para cada fila de chamadas ou atendimento automático do Sistema de Telefonia e dê a cada um deles um nome, endereço sip e assim `New-CsHybridApplicationEndpoint` por diante.

    ``` Powershell
    New-CsHybridApplicationEndpoint -DisplayName appinstance01 -SipAddress sip:appinstance01@litwareinc.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    Consulte [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) para obter mais detalhes sobre este comando.

2. (Opcional) Depois que suas contas de recursos são criadas, você pode esperar que o AD seja sincronizado entre online e local ou forçar uma sincronização e prosseguir com a configuração online do atendente automático do Sistema de Telefonia ou filas de chamadas. Para forçar uma sincronização, execute o seguinte comando no computador que executa o AAD Connect (se ainda não tiver feito isso, será necessário carregar para executar `import-module adsync` o comando):

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    Consulte [Start-ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) para obter mais detalhes sobre esse comando.

3. Crie o atendente automático ou fila de chamadas do Sistema de Telefonia. Confira um dos procedimentos a seguir:
   - [Configurar um atendedor automático do Cloud](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [Criar uma fila de chamada do Cloud](/MicrosoftTeams/create-a-phone-system-call-queue)  
4. Associe a conta de recurso e o atendente automático ou fila de chamadas do Sistema de Telefonia escolhido anteriormente.

## <a name="test-the-implementation"></a>Testar a implementação

A melhor maneira de testar a implementação é chamar o número configurado para um atendente automático ou fila de chamadas do Sistema de Telefonia e conectar-se a um dos agentes ou menus. Você também pode fazer rapidamente uma chamada de teste usando o **botão Testar** no painel ação do centro de administração. Se você quiser fazer alterações em um atendente automático ou fila de chamadas do Sistema de Telefonia, selecione-o e, no painel Ação, clique em **Editar.** 

> [!TIP]
> Se sua conta de recurso tiver dificuldades para ser atribuída a uma fila de chamada ou a um atendente automático, confira Problemas conhecidos do [Microsoft Teams](/MicrosoftTeams/Known-issues#phone-system) e a seção Como corrigir minhas [instâncias](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521) de aplicativo híbrido no Blog do Microsoft Teams.

## <a name="moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system"></a>Mover um atendente automático ou fila de chamadas da UM do Exchange para o Sistema de Telefonia

A migração da UM do Exchange para o Sistema de Telefonia exigirá a recriação da fila de chamadas e da estrutura do atendimento automático, não há suporte para a migração direta de um para o outro. Para implementar um conjunto de filas de chamada e de atendimentos automáticos:

1. Obter uma lista de todos os atendentes automáticos de UM do Exchange e filas de chamada executando o seguinte comando no sistema Exchange 2013 ou 2016 enquanto estiver conectado como administrador:

    ``` Powershell
    Get-UMAutoAttendant | Format-List
    ```

2. Para cada fila de chamada de UM do Exchange listada ou o atendente automático, anote seu lugar na estrutura, nas configurações e receba cópias dos arquivos de som ou de texto em fala associados (o guid na saída será o nome de uma pasta onde os arquivos estão armazenados). Você pode obter esses detalhes executando o comando:

    ``` Powershell
    Get-UMAutoAttendant -Identity MyUMAutoAttendant
    ```

    Consulte [Get-UMAutoAttendant](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/get-umautoattendant?view=exchange-ps) para obter mais detalhes sobre este comando. Uma lista completa das opções que talvez seja necessário capturar está nos membros [UMAutoAttendant,](https://msdn.microsoft.com/library/microsoft.exchange.data.directory.systemconfiguration.umautoattendant_members.aspx) mas as opções mais importantes a observar são:

    - Horário comercial
    - Horário não comercial
    - Idioma
    - Agendamento de Feriado

3. Crie novos pontos de extremidade locais conforme descrito anteriormente.
   Atribua ao atendente automático de nível superior um número temporário para fins de teste.

4. Configure um atendente automático ou fila de chamadas do Sistema de Telefonia que use os pontos de extremidade conforme descrito anteriormente.

5. Teste o atendente automático ou a fila de chamadas do Sistema de Telefonia.

6. Reatribuir o número de telefone vinculado à fila de chamadas da UM do Exchange ou ao atendente automático do Sistema de Telefonia correspondente ou à fila de chamadas.  

   Neste ponto, se você já migrou a caixa postal da UM, deve estar em posição de migrar para o Exchange Server 2019.

## <a name="see-also"></a>Confira também

[Criar uma fila de chamada do Cloud](/MicrosoftTeams/create-a-phone-system-call-queue)

[Quais são os atendedores automáticos do Cloud?](/MicrosoftTeams/what-are-phone-system-auto-attendants)

[Configurar um atendedor automático do Cloud](/MicrosoftTeams/create-a-phone-system-auto-attendant)  

[Atendedores automáticos do plano da nuvem](plan-cloud-auto-attendant.md)

[Planejar filas de chamadas da nuvem](plan-call-queue.md)

[Planejar o serviço de Caixa Postal na Nuvem para usuários locais](plan-cloud-voicemail.md)

[New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

[Gerenciar contas de recursos no Microsoft Teams](/MicrosoftTeams/manage-resource-accounts)  -  \( para criar contas de recursos ativas online\)
