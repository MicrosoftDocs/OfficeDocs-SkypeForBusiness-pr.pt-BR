---
title: Configurar uma conta de recurso no Skype for Business Server 2019
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: wasseemh
ms.audience: ITPro
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Configurar uma conta de recurso para o Skype for Business Server 2019.
ms.openlocfilehash: a307a5ed40c52579020f4cd0eef6646afdb15649
ms.sourcegitcommit: 5ec5df597614d402917e0585575dd69acda22172
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/08/2019
ms.locfileid: "36253950"
---
# <a name="configure-resource-accounts"></a>Configurar contas de recurso

As implementações híbridas do Skype for Business Server 2019 usam apenas serviços em nuvem fornecidos pelo sistema de telefonia para Unificação de mensagens e não se integram ao Exchange Online. No Skype for Business Server 2019, agora você pode usar as filas de chamadas de nuvem e atendedores automáticos descritos [aqui, o que você obtém com o sistema de telefonia no Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system).

Para usar um atendedor automático do sistema de telefonia ou uma fila de chamadas com o Skype for Business Server 2019, você precisará criar contas de recursos que atuem como pontos de extremidade de aplicativo e podem receber números de telefone e usar o centro de administração do teams online para configurar a fila de chamadas ou atendedor automático. Essa conta de recurso pode ser hospedada online (Confira [gerenciar contas de recursos no Microsoft Teams](/MicrosoftTeams/manage-resource-accounts) para criar contas de recursos hospedadas online) ou local, conforme descrito neste artigo. Normalmente, você terá vários nós de atendedor automático ou de enfileiramento de sistema de telefonia, cada um deles mapeado para contas de recursos, que podem estar hospedados online ou no Skype for Business Server 2019.

Se você tiver um atendedor automático de UM do Exchange e um sistema de fila de chamadas, antes de mudar para o Exchange Server 2019 ou Exchange Online, será necessário registrar manualmente os detalhes conforme descrito abaixo e implementar um sistema completamente novo usando o centro de administração do Microsoft Teams .

## <a name="overview"></a>Visão geral

Se o atendedor automático ou a fila de chamadas do sistema de telefonia precisar de um número de serviço, as várias dependências poderão ser atendidas na seguinte sequência:

1. Obter um número de serviço
2. Obter um sistema de telefonia livre- [licença de usuário virtual](/MicrosoftTeams/teams-add-on-licensing/virtual-user) ou uma licença de sistema de telefonia pago para usar com a conta de recurso.
3. Criar a conta de recurso. Um atendedor automático ou fila de chamada é necessário para ter uma conta de recurso associada.
4. Aguarde uma sincronização do Active Directory entre online e local.
5. Atribua a licença do sistema de telefonia à conta de recurso.
6. Atribuir um número de serviço à conta de recurso.
7. Criar uma fila de chamadas do sistema de telefonia ou atendedor automático.
8. Associe a conta de recurso a um atendedor automático ou a uma fila de chamada: (New-CsApplicationInstanceAssociation).

Se o atendedor automático ou a fila de chamadas estiverem aninhados em um atendedor automático de nível superior, a conta de recurso associada só precisará de um número de telefone se você quiser vários pontos de entrada na estrutura de atendedores automáticos e filas de chamada.

Para redirecionar as chamadas para pessoas em sua organização que estão hospedadas online, elas devem ter uma licença de **sistema de telefonia** e estar habilitadas para o Enterprise Voice ou ter planos de chamadas do Office 365. Consulte [atribuir licenças do Microsoft Teams](/MicrosoftTeams/assign-teams-licenses). Para habilitá-los para o Enterprise Voice, você pode usar o Windows PowerShell. Por exemplo, execute:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

Se o atendedor automático do sistema de telefonia ou a fila de chamada que você estiver criando for aninhado e não precisar de um número de telefone, o processo será:

1. Criar a conta de recurso  
2. Aguardar uma sincronização do Active Directory entre online e local
3. Criar um atendedor automático ou fila de chamadas do sistema de telefonia
4. Associar a conta de recurso a um atendedor automático ou a uma fila de chamadas do sistema de telefonia

## <a name="create-a-resource-account-with-a-phone-number"></a>Criar uma conta de recurso com um número de telefone

A criação de uma conta de recurso que usa um número de telefone precisaria executar as seguintes tarefas na seguinte ordem:

1. Porta ou obter um número de serviço de chamada tarifada ou gratuita. O número não pode ser atribuído a nenhum outro serviço de voz ou contas de recurso.

   Antes de atribuir um número de telefone a uma conta de recurso, você precisará obter ou portar os números de serviço de chamada gratuita ou tarifada existentes. Após obter os números de telefone de serviço de chamada tarifada ou gratuita, eles serão exibidos nos**números de telefone**de**voz** > do **Centro** > de administração do Microsoft Teams e o **tipo de número** listado será listado como **serviço de chamada**gratuita. Para obter seus números de serviço, consulte [obter números de telefone de serviço](/MicrosoftTeams/getting-service-phone-numbers) ou se você deseja transferir um número de serviço existente, consulte [transferir números de telefone para o Office 365](/MicrosoftTeams/transfer-phone-numbers-to-office-365).

   Se você estiver fora dos Estados Unidos, não poderá usar o centro de administração do Microsoft Teams para obter os números de serviço. Vá para [gerenciar números de telefone para sua organização](/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization) em vez de ver como fazer isso fora dos Estados Unidos.

2. Comprar uma licença do sistema de telefonia. Confira:  
   - [Sistema de telefonia – licença de usuário virtual](/MicrosoftTeams/teams-add-on-licensing/virtual-user.md)
   - [Office 365 Enterprise E1 e E3](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e1-e3)
   - [Office 365 Enterprise E5](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e5-with-audio-conferencing)
   - [Software comercial do Office 365 Enterprise e5](https://products.office.com/business/office-365-enterprise-e5-business-software)

3. Crie uma conta de recurso local executando o `New-CsHybridApplicationEndpoint` cmdlet para cada atendedor automático do sistema de telefonia ou fila de chamadas e dê um nome, endereço SIP e assim por diante.

    ``` Powershell
    New-CsHybridApplicationEndpoint -DisplayName appinstance01 -SipAddress sip:appinstance01@contoso.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    Consulte [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) para obter mais detalhes sobre este comando.

4. Opcion Depois que suas contas de recursos são criadas, você pode aguardar que o AD seja sincronizado entre online e local, ou forçar uma sincronização e prosseguir para a configuração online de atendedor automático ou filas de chamadas do sistema de telefonia. Para forçar uma sincronização, você deve executar o seguinte comando no computador que está executando o AAD Connect (se você ainda não tiver feito isso, `import-module adsync` você precisará carregar para executar o comando):

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    Consulte [Start-ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) para obter mais detalhes sobre este comando.

5. Atribua a licença de usuário virtual ou de sistema de telefonia à conta de recurso. Consulte [atribuir licenças do Microsoft Teams](/MicrosoftTeams/assign-teams-licenses) e [atribuir licenças a um usuário](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user).

   Se você estiver atribuindo um número de telefone a uma conta de recurso, agora você pode usar o sistema de telefonia livre de custo-licença de usuário virtual. Isso fornece recursos do sistema de telefonia para números de telefone no nível organizacional e permite que você crie recursos de atendedor automático e fila de chamadas.


6. Atribua o número de serviço à conta de recurso. Use o `Set-CsHybridApplicationEndpoint` comando para atribuir um número de telefone (com a opção-LineURI) à conta de recurso.

    ``` Powershell
    Set-CsHybridApplicationEndpoint -Identity appinstance01@contoso.com -LineURI tel:+14255550100
    ```

    Consulte [set-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/set-cshybridapplicationendpoint?view=skype-ps) para obter mais detalhes sobre este comando.

    Para atribuir um roteamento direto ou número híbrido a uma conta de recurso, use o seguinte cmdlet:

   ``` Powershell
   Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
   ```

A conta do recurso precisará de um número de telefone atribuído se ele for atribuído a um atendedor automático de nível superior ou a fila de chamadas. Os números de telefone do usuário (assinante) não podem ser atribuídos a uma conta de recurso, somente os números de telefone de chamada tarifada ou gratuita de serviço podem ser usados.

  Você pode atribuir um número híbrido de roteamento direto à sua conta de recurso.  Consulte [Plan Direct Routing](/MicrosoftTeams/direct-routing-plan.md) para obter detalhes.

  > [!NOTE]
  > Os números de serviço de roteamento direto atribuídos às contas de recursos para atendedor automático e filas de chamada têm suporte apenas para usuários e agentes do Microsoft Teams.

7. Crie o atendedor automático do sistema de telefonia ou a fila de chamadas. Confira um dos procedimentos a seguir:

   - [Configurar um atendedor automático na nuvem](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [Criar uma fila de chamada em nuvem](/MicrosoftTeams/create-a-phone-system-call-queue)  

8. Associe a conta de recurso ao atendedor automático ou à fila de chamadas do sistema de telefonia que você escolheu anteriormente.

Um exemplo de uma implementação de pequena empresa está disponível no [exemplo de pequena empresa-configurar um atendedor automático e um](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa.yml) [exemplo de pequena empresa-configurar uma fila de chamadas](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-cq.yml).

## <a name="create-a-resource-account-without-a-phone-number"></a>Criar uma conta de recurso sem um número de telefone

Esta seção discute a criação de uma conta de recurso que está hospedada no local. A criação de uma conta de recurso que está hospedada online é abordada em [gerenciar contas de recursos no Microsoft Teams](/MicrosoftTeams/manage-resource-accounts).

Essas etapas são necessárias se você estiver criando um atendedor automático do sistema de telefonia ou uma estrutura de fila de chamada novo, ou reconstruindo a estrutura originalmente criada no UM do Exchange.

Faça logon no servidor front-end do Skype for Business e execute os seguintes cmdlets do PowerShell:

1. Crie uma conta de recurso local executando o `New-CsHybridApplicationEndpoint` cmdlet para cada atendedor automático do sistema de telefonia ou fila de chamadas e dê um nome, endereço SIP e assim por diante.

    ``` Powershell
    New-CsHybridApplicationEndpoint -DisplayName appinstance01 -SipAddress sip:appinstance01@litwareinc.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    Consulte [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) para obter mais detalhes sobre este comando.

2. Opcion Depois que suas contas de recursos são criadas, você pode aguardar que o AD seja sincronizado entre online e local, ou forçar uma sincronização e prosseguir para a configuração online de atendedor automático ou filas de chamadas do sistema de telefonia. Para forçar uma sincronização, você deve executar o seguinte comando no computador que está executando o AAD Connect (se você ainda não tiver feito isso, `import-module adsync` você precisará carregar para executar o comando):

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    Consulte [Start-ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) para obter mais detalhes sobre este comando.

3. Crie o atendedor automático do sistema de telefonia ou a fila de chamadas. Confira um dos procedimentos a seguir:
   - [Configurar um atendedor automático na nuvem](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [Criar uma fila de chamada em nuvem](/MicrosoftTeams/create-a-phone-system-call-queue)  
4. Associe a conta de recurso e o atendedor automático ou a fila de chamadas do sistema de telefonia que você escolheu anteriormente.

Um exemplo de uma implementação de pequena empresa está disponível no [exemplo de pequena empresa-configurar um atendedor automático e um](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa.yml) [exemplo de pequena empresa-configurar uma fila de chamadas](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-cq.yml).

## <a name="test-the-implementation"></a>Testar a implementação

A melhor maneira de testar a implementação é chamar o número configurado para um atendedor automático do sistema de telefonia ou uma fila de chamadas e se conectar a um dos agentes ou menus. Você também pode colocar rapidamente uma chamada de teste usando o **botão testar** no painel de ações do centro de administração. Se você quiser fazer alterações em um atendedor automático ou na fila de chamadas do sistema de telefonia, selecione-a e, em seguida, no painel de ações, clique em **Editar**.

## <a name="moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system"></a>Mover um atendedor automático ou fila de chamadas do UM do Exchange para o sistema de telefonia

A migração do Exchange UM para o sistema de telefonia exigirá a recriação da fila de chamadas e da estrutura de atendedor automático, não há suporte para migrar diretamente de um para o outro. Para reimplementar um conjunto de filas de chamadas e atendedores automáticos:

1. Obtenha uma lista de todos os atendedores automáticos e filas de chamadas do UM do Exchange executando o seguinte comando no sistema do Exchange 2013 ou 2016 enquanto estiver conectado como administrador:

    ``` Powershell
    Get-UMAutoAttendant | Format-List
    ```

2. Para cada fila de chamadas ou atendedor automático de UM do Exchange listado, observe seu lugar na estrutura, as configurações e Obtenha cópias de arquivos de som ou texto para fala associados (o GUID na saída será o nome de uma pasta onde os arquivos estão armazenados). Você pode obter estes detalhes executando o comando:

    ``` Powershell
    Get-UMAutoAttendant -Identity MyUMAutoAttendant
    ```

    Consulte [Get-UMAutoAttendant](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/get-umautoattendant?view=exchange-ps) para obter mais detalhes sobre este comando. Uma lista completa de opções que talvez você precise capturar é em [membros do UMAutoAttendant](https://msdn.microsoft.com/library/microsoft.exchange.data.directory.systemconfiguration.umautoattendant_members.aspx) , mas as opções mais importantes a serem anotadas são:

    - Horário comercial
    - Horário não comercial
    - Idioma
    - Agendamento de Feriado

3. Crie novos pontos de extremidade locais, conforme descrito anteriormente.
   Atribua o atendedor automático de nível superior um número temporário para fins de teste.

4. Configure um atendedor automático do sistema de telefonia ou uma fila de chamada que usa os pontos de extremidade, conforme descrito anteriormente.

   Você pode achar útil usar os exercícios no tutorial intitulado [Small Business example-configurar um atendedor automático](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa.yml) para criar um mapa lógico das hierarquias em seu antigo sistema de um do Exchange.
5. Teste o atendedor automático do sistema de telefonia ou a fila de chamadas.
6. Reatribua o número de telefone vinculado à fila de chamadas da UM do Exchange ou ao atendedor automático ao atendedor automático ou à fila de chamadas do sistema de telefonia correspondente.  

   Neste ponto, se você já tiver migrado UM caixa postal de UM, você deve estar em uma posição para migrar para o Exchange Server 2019.

## <a name="see-also"></a>Confira também

[Criar uma fila de chamada em nuvem](/MicrosoftTeams/create-a-phone-system-call-queue)

[O que são atendedores automáticos de nuvem?](/MicrosoftTeams/what-are-phone-system-auto-attendants)

[Configurar um atendedor automático na nuvem](/MicrosoftTeams/create-a-phone-system-auto-attendant)  

[Planejar atendedores automáticos de nuvem](plan-cloud-auto-attendant.md)

[Planejar filas de chamada em nuvem](plan-call-queue.md)

[Planejar o serviço de caixa postal na nuvem para usuários locais](plan-cloud-voicemail.md)

[New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

[Gerenciar contas de recursos no Microsoft Teams](/MicrosoftTeams/manage-resource-accounts) - \(para criar contas de recursos hospedadas online\)
