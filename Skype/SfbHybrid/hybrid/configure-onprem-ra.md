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
ms.localizationpriority: medium
ms.collection: ''
description: Configure uma conta de recurso para Skype for Business Server 2019.
ms.openlocfilehash: ebaf79229097df8d3477b4d9b74504c278bfd59c
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/05/2022
ms.locfileid: "66615607"
---
# <a name="configure-resource-accounts"></a>Configurar contas de recurso

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Skype for Business Server implementações híbridas de 2019 usam apenas serviços de nuvem fornecidos pelo Sistema de Telefonia para unificação de mensagens e não se integram ao Exchange Online. No Skype for Business Server 2019, agora você pode usar as filas de chamadas na nuvem e os atendedores automáticos descritos em Aqui está o que você obtém com o Sistema de Telefonia no [Microsoft 365 ou Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system).

Para usar um atendedor automático do Sistema de Telefonia ou uma fila de chamadas com o Skype for Business Server 2019, você precisará criar contas de recursos que atuam como pontos de extremidade do aplicativo e podem receber números de telefone e, em seguida, usar o centro de administração online do Teams para configurar a fila de chamadas ou o atendedor automático. Essa conta de recurso pode ser hospedado online (consulte Gerenciar contas de recursos no [Microsoft Teams](/MicrosoftTeams/manage-resource-accounts) para criar contas de recursos hospedados online) ou localmente, conforme descrito neste artigo. Normalmente, você terá vários atendedores automáticos do Sistema de Telefonia ou nós de fila de chamadas, cada um deles mapeado para uma conta de recurso, que pode ser hospedado online ou no Skype for Business Server 2019.

Se você tiver um atendedor automático do Exchange UM e um sistema de fila de chamadas existentes, antes de alternar para o Exchange Server 2019 ou o Exchange Online, será necessário registrar manualmente os detalhes conforme descrito abaixo e implementar um sistema completamente novo usando o Centro de administração do Teams.

## <a name="overview"></a>Visão Geral

Se o atendedor automático ou a fila de chamadas do Sistema de Telefonia precisar de um número de serviço, as várias dependências poderão ser atendidas na seguinte sequência:

1. Obter um número de serviço.
2. Obtenha uma licença [Telefonia do Microsoft Teams conta de recurso gratuita](/MicrosoftTeams/teams-add-on-licensing/virtual-user) ou uma licença paga do Sistema de Telefonia para usar com a conta de recurso.
3. Crie a conta de recurso. Um atendedor automático ou fila de chamadas é necessário para ter uma conta de recurso associada.
4. Aguarde uma sincronização do Active Directory entre online e local.
5. Atribua a licença do Sistema de Telefonia à conta de recurso.
6. Atribua um número de serviço à conta de recurso.
7. Crie uma fila de chamadas do Sistema de Telefonia ou atendedor automático.
8. Associe a conta de recurso a um atendedor automático ou fila de chamadas: (New-CsApplicationInstanceAssociation).

Se o atendedor automático ou fila de chamadas estiver aninhado em um atendedor automático de nível superior, a conta de recurso associada só precisará de um número de telefone se você quiser vários pontos de entrada na estrutura de atendedores automáticos e filas de chamadas.

Para redirecionar chamadas para pessoas em sua organização que estão hospedados online, elas devem ter  uma licença do Sistema de Telefonia e estar habilitadas para o Enterprise Voice ou ter Planos de Chamadas do Microsoft 365 ou Office 365. Consulte [Atribuir licenças do Microsoft Teams](/MicrosoftTeams/assign-teams-licenses). Para habilita-Enterprise Voice, você pode usar Windows PowerShell. Por exemplo, execute:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

Se o atendedor automático do sistema de telefonia ou a fila de chamadas que você está criando estiver aninhado e não precisar de um número de telefone, o processo será:

1. Criar a conta de recurso  
2. Aguardar uma sincronização do Active Directory entre online e local
3. Criar um atendedor automático do Sistema de Telefonia ou fila de chamadas
4. Associar a conta de recurso a um atendedor automático do Sistema de Telefonia ou fila de chamadas

## <a name="create-a-resource-account-with-a-phone-number"></a>Criar uma conta de recurso com um número de telefone

A criação de uma conta de recurso que usa um número de telefone exigiria a execução das seguintes tarefas na seguinte ordem:

1. Portar ou obter um número de serviço de chamada tarifada ou gratuita. O número não pode ser atribuído a nenhum outro serviço de voz ou contas de recurso.

   Antes de atribuir um número de telefone a uma conta de recurso, você precisará obter ou portar seus números de serviço de chamada tarifada ou gratuita existentes. Depois que você receber os números de telefone de serviço de chamada tarifada ou gratuita, eles aparecerão nos números de telefone de voz do centro  de administração do **Microsoft Teams** >  > **, e** o tipo de número listado será listado como Serviço **–** Chamada Gratuita. Para obter seus números de serviço, consulte [Obtendo](/MicrosoftTeams/getting-service-phone-numbers) números de telefone de serviço ou se você deseja transferir um número de serviço existente, consulte [Transferir números de telefone para o Teams](/MicrosoftTeams/phone-number-calling-plans/transfer-phone-numbers-to-teams).

   Se você estiver fora do Estados Unidos, não poderá usar o centro de administração do Microsoft Teams para obter números de serviço. Em vez [disso, acesse Gerenciar números de](/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization) telefone da sua organização para ver como fazê-lo de fora do Estados Unidos.

2. Compre uma licença do Sistema de Telefonia. Confira:  
   - [Telefonia do Microsoft Teams conta de recurso](/MicrosoftTeams/teams-add-on-licensing/virtual-user)
   - [Office 365 Enterprise E1 e E3](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e1-e3)
   - [Office 365 Enterprise E5](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e5-with-audio-conferencing)
   - [Office 365 Enterprise E5 Business Software](https://products.office.com/business/office-365-enterprise-e5-business-software)

3. Crie uma conta de `New-CsHybridApplicationEndpoint` recurso local executando o cmdlet para cada atendedor automático do Sistema de Telefonia ou fila de chamadas e dê a cada um deles um nome, endereço sip e assim por diante.

    ``` Powershell
    New-CsHybridApplicationEndpoint -ApplicationID <GUID> -DisplayName appinstance01 -SipAddress sip:appinstance01@contoso.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    Consulte [New-CsHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) para obter mais detalhes sobre esse comando.

4. (Opcional) Depois que suas contas de recursos forem criadas, você poderá aguardar o AD sincronizar entre o local e online ou forçar uma sincronização e prosseguir para a configuração online do atendedor automático do Sistema de Telefonia ou filas de chamadas. Para forçar uma sincronização, execute o seguinte comando no computador que executa o AAD Connect ( `import-module adsync` se você ainda não fez isso, precisará carregar para executar o comando):

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    Consulte [Start-ADSyncSyncCycle para](/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) obter mais detalhes sobre esse comando.

    Observe que, neste ponto, a conta pode ter sido sincronizada, mas o provisionamento pode não estar concluído.  Verifique a saída de [Get-CsOnlineApplicationEndpoint](/powershell/module/skype/get-csonlineapplicationendpoint).  Se o ponto de extremidade sincronizado ainda não tiver concluído o provisionamento, ele não aparecerá aqui.  Você pode verificar o status das solicitações de provisionamento no portal do M365 em [Status de Instalação do Teams](https://admin.microsoft.com/AdminPortal/Home#/teamsprovisioning).  Essa fase de provisionamento pode levar até 24 horas.

5. Atribua **a Telefonia do Microsoft Teams conta de recurso** **ou Telefonia do Teams Padrão** licença à conta de recurso. Confira [Atribuir licenças de complemento do Microsoft Teams](/MicrosoftTeams/teams-add-on-licensing/assign-teams-add-on-licenses) e [atribuir licenças aos usuários](/microsoft-365/admin/manage/assign-licenses-to-users).

   Se você estiver atribuindo um número de telefone a uma conta de recurso, agora poderá usar a licença gratuita Telefonia do Microsoft Teams **conta de** recurso. Isso fornece recursos do Sistema de Telefonia para números de telefone no nível organizacional e permite que você crie funcionalidades de atendedor automático e fila de chamadas.

6. Atribua o número de serviço à conta de recurso. Use o `Set-CsHybridApplicationEndpoint` comando para atribuir um número de telefone (com a opção -LineURI) à conta de recurso.

    ``` Powershell
    Set-CsHybridApplicationEndpoint -Identity appinstance01@contoso.com -LineURI tel:+14255550100
    ```

    Consulte [Set-CsHybridApplicationEndpoint](/powershell/module/skype/set-cshybridapplicationendpoint?view=skype-ps) para obter mais detalhes sobre esse comando.

    Para atribuir um Roteamento Direto ou um número híbrido a uma conta de recurso, use o seguinte cmdlet:

   ``` Powershell
   Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
   ```

   A conta de recurso precisará de um número de telefone atribuído se ele for atribuído a um atendedor automático de nível superior ou fila de chamadas. Os números de telefone de usuário (assinante) não podem ser atribuídos a uma conta de recurso, somente números de chamada tarifada ou de chamada gratuita podem ser usados.

     Você pode atribuir um Roteamento Direto ou um número híbrido à sua conta de recurso. Para obter detalhes, consulte [Plan Direct Routing and](/MicrosoftTeams/direct-routing-plan) [Plan Cloud auto attendants](plan-cloud-auto-attendant.md).

     > [!NOTE]
     > Os números de serviço de Roteamento Direto atribuídos a contas de recursos para atendedor automático e filas de chamadas têm suporte apenas para usuários e agentes do Microsoft Teams.

7. Crie o atendedor automático do Sistema de Telefonia ou a fila de chamadas. Confira um dos procedimentos a seguir:

   - [Configurar um atendedor automático do Cloud](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [Criar uma fila de chamada do Cloud](/MicrosoftTeams/create-a-phone-system-call-queue)  

8. Associe a conta de recurso ao atendedor automático do Sistema de Telefonia ou à fila de chamadas escolhida anteriormente.

## <a name="create-a-resource-account-without-a-phone-number"></a>Criar uma conta de recurso sem um número de telefone

Esta seção discute a criação de uma conta de recurso que é hospedado no local. A criação de uma conta de recurso que é hospedado online é discutida em [Gerenciar contas de recursos no Microsoft Teams](/MicrosoftTeams/manage-resource-accounts).

Essas etapas são necessárias se você estiver criando um atendedor automático do Sistema de Telefonia ou uma estrutura de fila de chamadas, ou recriando a estrutura criada originalmente no Exchange UM.

Faça logon no Skype for Business front-end e execute os seguintes cmdlets do PowerShell:

1. Crie uma conta de `New-CsHybridApplicationEndpoint` recurso local executando o cmdlet para cada atendedor automático do Sistema de Telefonia ou fila de chamadas e dê a cada um deles um nome, endereço sip e assim por diante.

    ``` Powershell
    New-CsHybridApplicationEndpoint -DisplayName appinstance01 -SipAddress sip:appinstance01@litwareinc.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    Consulte [New-CsHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) para obter mais detalhes sobre esse comando.

2. (Opcional) Depois que suas contas de recursos forem criadas, você poderá aguardar o AD sincronizar entre o local e online ou forçar uma sincronização e prosseguir para a configuração online do atendedor automático do Sistema de Telefonia ou filas de chamadas. Para forçar uma sincronização, execute o seguinte comando no computador que executa o AAD Connect ( `import-module adsync` se você ainda não fez isso, precisará carregar para executar o comando):

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    Consulte [Start-ADSyncSyncCycle para](/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) obter mais detalhes sobre esse comando.

3. Crie o atendedor automático do Sistema de Telefonia ou a fila de chamadas. Confira um dos procedimentos a seguir:
   - [Configurar um atendedor automático do Cloud](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [Criar uma fila de chamada do Cloud](/MicrosoftTeams/create-a-phone-system-call-queue)  
4. Associe a conta de recurso e o atendedor automático do Sistema de Telefonia ou a fila de chamadas escolhida anteriormente.

## <a name="test-the-implementation"></a>Testar a implementação

A melhor maneira de testar a implementação é chamar o número configurado para um atendedor automático ou fila de chamadas do Sistema de Telefonia e conectar-se a um dos agentes ou menus. Você também pode fazer uma chamada de teste rapidamente usando o **botão Testar** no painel Ação do centro de administração. Se você quiser fazer alterações em um atendedor automático do Sistema de Telefonia ou fila de chamadas, selecione-o e, no painel Ação, clique em **Editar**. 

> [!TIP]
> Se sua conta de recurso tiver dificuldades para ser atribuída a uma fila de chamadas ou atendedor automático, consulte Problemas conhecidos do [Microsoft Teams](/MicrosoftTeams/Known-issues#phone-system) e a seção Como corrigir minhas [instâncias](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521) de aplicativo híbrido no Blog do Microsoft Teams.

## <a name="moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system"></a>Mover um atendedor automático da UNIFICAção do Exchange ou uma fila de chamadas para o Sistema de Telefonia

A migração do Exchange UM para o Sistema de Telefonia exigirá a recriação da fila de chamadas e da estrutura do atendedor automático, não há suporte para a migração direta de uma para a outra. Para implementar novamente um conjunto de filas de chamadas e atendedores automáticos:

1. Obtenha uma lista de todos os atendedores automáticos e filas de chamadas do Exchange executando o seguinte comando no sistema Exchange 2013 ou 2016 enquanto estiver conectado como administrador:

    ``` Powershell
    Get-UMAutoAttendant | Format-List
    ```

2. Para cada fila de chamadas ou atendedor automático de chamadas do Exchange listado, anote seu lugar na estrutura, nas configurações e obtenha cópias de arquivos de som ou de conversão de texto em fala associados (o guid na saída será o nome de uma pasta em que os arquivos são armazenados). Você pode obter esses detalhes executando o comando:

    ``` Powershell
    Get-UMAutoAttendant -Identity MyUMAutoAttendant
    ```

    Consulte [Get-UMAutoAttendant](/powershell/module/exchange/unified-messaging/get-umautoattendant?view=exchange-ps) para obter mais detalhes sobre este comando. Uma lista completa de opções que talvez seja necessário capturar está em [membros UMAutoAttendant](/previous-versions/office/exchange-server-api/ff340649(v=exchg.150)) , mas as opções mais importantes a serem observadas são:

    - Horário comercial
    - Horário comercial
    - Idioma
    - Agendamento de Feriado

3. Crie novos pontos de extremidade locais conforme descrito anteriormente.
   Atribua ao atendedor automático de nível superior um número temporário para fins de teste.

4. Configure um atendedor automático do Sistema de Telefonia ou uma fila de chamadas que use os pontos de extremidade conforme descrito anteriormente.

5. Teste o atendedor automático do Sistema de Telefonia ou a fila de chamadas.

6. Reatribua o número de telefone vinculado à fila de chamadas da UNIFICAção do Exchange ou ao atendedor automático do Sistema de Telefonia correspondente ou à fila de chamadas.  

   Neste ponto, se você já migrou a Caixa Postal da UNIFICAÇÃO, deverá estar em posição de migrar para o Exchange Server 2019.

## <a name="see-also"></a>Confira também

[Criar uma fila de chamada do Cloud](/MicrosoftTeams/create-a-phone-system-call-queue)

[Quais são os atendedores automáticos do Cloud?](/MicrosoftTeams/what-are-phone-system-auto-attendants)

[Configurar um atendedor automático do Cloud](/MicrosoftTeams/create-a-phone-system-auto-attendant)  

[Atendedores automáticos do plano da nuvem](plan-cloud-auto-attendant.md)

[Planejar filas de chamadas da nuvem](plan-call-queue.md)

[Planejar Caixa postal na Nuvem serviço para usuários locais](plan-cloud-voicemail.md)

[New-CsHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[New-CsOnlineApplicationInstance](/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

[Gerenciar contas de recursos no Microsoft Teams](/MicrosoftTeams/manage-resource-accounts) - \( para criar contas de recursos hospedados online\)