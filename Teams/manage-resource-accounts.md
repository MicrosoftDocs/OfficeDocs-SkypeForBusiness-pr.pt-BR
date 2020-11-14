---
title: Gerenciar contas de recursos no Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: jastark, wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
- seo-marvel-apr2020
description: Neste artigo, você aprenderá a criar, editar e gerenciar contas de recursos no Microsoft Teams.
ms.openlocfilehash: 2a043b608dfe311003dea26acc8a0c236460fad5
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031017"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a>Gerenciar contas de recursos no Microsoft Teams

Uma conta de recurso é um objeto de usuário desabilitado no Azure AD e pode ser usada para representar recursos em geral. Por exemplo, uma conta de recurso pode ser usada no Exchange para representar salas de conferência e permitir que elas tenham um número de telefone e um calendário. Uma conta de recurso pode ser hospedada no Microsoft 365 ou em instalações locais usando o Skype for Business Server 2019.

No Microsoft Teams, uma conta de recurso é necessária para cada atendedor automático ou fila de chamadas. As contas de recursos também podem ser atribuídas a números de telefone de serviço. É assim que você atribui números de telefone a atendedores automáticos e filas de chamadas, permitindo que os chamadores de equipes externas atinjam o atendedor automático ou a fila de chamadas.

Este artigo aborda como criar contas de recursos e prepará-las para uso com atendedores automáticos e filas de chamadas.

Antes de iniciar os procedimentos deste artigo, verifique se você fez o seguinte:

- [Obter licenças de usuário virtual](#obtain-virtual-user-licenses)
- [Obter números de serviço](#obtain-service-numbers)

### <a name="obtain-virtual-user-licenses"></a>Obter licenças de usuário virtual

Cada conta de recurso requer uma licença para funcionar com atendedores automáticos e filas de chamadas. Você pode usar um *sistema telefônico gratuito Microsoft 365-licença de usuário virtual* . Para obter essas licenças, consulte [licença de usuário virtual](teams-add-on-licensing/virtual-user.md).

Nós abordamos como atribuir a licença a uma conta de recurso mais adiante neste artigo.

Para obter a licença de usuário virtual, no centro de administração do Microsoft 365, **Billing** acesse  >  **Purchase services**  >  **assinaturas complementares** de serviços de compra de cobrança e role até o fim-você verá *sistema telefônico-licença de usuário virtual* . Selecione **comprar agora**. Há um custo zero, mas você ainda precisa seguir estas etapas para adquirir a licença.

### <a name="obtain-service-numbers"></a>Obter números de serviço

Os números de serviço são opcionais para atendedores automáticos e filas de chamadas, mas você precisará pelo menos um número de serviço para que os chamadores atinjam o atendedor automático e a configuração da fila de chamadas. Para qualquer atendedor automático ou fila de chamadas que você deseja que seja alcançável diretamente por um número de serviço, você deve ter uma conta de recurso com um número de serviço associado.

As contas de recursos podem usar números de serviço de chamada tarifada ou gratuita. Você pode solicitar novos números ou portar números existentes de outra operadora.

Para obter novos números de serviço, consulte [obtendo números de telefone de serviço](getting-service-phone-numbers.md).

Para portar um número de outra operadora, confira [transferir números de telefone para o Microsoft Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).

## <a name="create-a-resource-account"></a>Criar uma conta de recurso

Você pode criar uma conta de recurso no centro de administração do Microsoft Teams.

![Captura de tela da interface do usuário da conta adicionar recurso](media/resource-account-add.png)

1. No centro de administração do Teams, expanda **configurações de toda a organização** e clique em **contas de recursos**.

2. Clique em **Adicionar**.

3. No painel **adicionar conta do recurso** , preencha o **nome para exibição** , o nome de **usuário** e o tipo de **conta do recurso**. O tipo de conta de recurso pode ser o **atendedor automático** ou a **fila de chamadas** , dependendo de como você pretende usar essa conta de recurso.

4. Clique em **Salvar**.

![Captura de tela de uma lista de contas de recursos](media/resource-accounts-page.png)

## <a name="assign-a-license"></a>Atribuir uma licença

Para cada conta de recurso, você deve atribuir um *sistema telefônico Microsoft 365-licença de usuário virtual* ou licença do *sistema de telefonia* .

![Captura de tela da interface do usuário de atribuir licenças no centro de administração do Microsoft 365](media/resource-account-assign-virtual-user-license.png)

1. No centro de administração do Microsoft 365, clique na conta de recurso à qual você deseja atribuir uma licença.

2. Na guia **licenças e aplicativos** , em **licenças** , selecione **sistema telefônico Microsoft 365-usuário virtual**.

3. Clique em **salvar alterações**.

## <a name="assign-a-service-number"></a>Atribuir um número de serviço

Se você estiver planejando usar a conta do recurso com um atendedor automático ou uma fila de chamadas que exija um número de serviço, atribua um número à conta do recurso.

![Captura de tela da interface de usuário atribuir número de serviço](media/resource-account-assign-phone-number.png)

1. No centro de administração do Teams, na página **contas do recurso** , selecione a conta do recurso à qual você deseja atribuir um número de serviço e clique em **atribuir/Cancelar atribuição**.

2. Na lista suspensa **tipo de número de telefone** , escolha o tipo de número que você deseja usar.

3. Na caixa **número de telefone atribuído** , procure o número que deseja usar e clique em **Adicionar**.

4. Clique em **Salvar**.


Para atribuir um roteamento direto ou número híbrido a uma conta de recurso, você precisa usar o PowerShell:

`Set-CsOnlineApplicationInstance -Identity aa-contoso_main@contoso64.net -OnpremPhoneNumber +19295550150`

## <a name="next-steps"></a>Próximas etapas

Depois de concluir a configuração da conta do recurso e atribuir um número de serviço, se necessário, você estará pronto para usar a conta do recurso com um atendedor automático ou uma fila de chamadas.

Consulte as seguintes referências:

 - [Atendedor automático na nuvem](create-a-phone-system-auto-attendant.md)

 - [Fila de chamadas em nuvem](create-a-phone-system-call-queue.md)

Você pode editar o nome para **exibição** da conta do recurso e o tipo de **conta do recurso** usando a opção **Editar** . Clique em **salvar** quando terminar.

## <a name="change-an-existing-resource-account-to-use-a-virtual-user-license"></a>Alterar uma conta de recurso existente para usar uma licença de usuário virtual

Se você decidir mudar as licenças de sua conta de recurso existente de uma licença do **sistema telefônico** para uma licença de usuário virtual, será necessário adquirir a licença de usuário virtual gratuita e, em seguida, seguir as etapas no centro de administração do Microsoft 365 para [mover os usuários para uma assinatura diferente](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription).

> [!WARNING]
> Sempre remova uma licença completa do sistema de telefonia e atribua a licença de usuário virtual na mesma atividade de licença. Se você remover a antiga licença, salvar as alterações da conta, adicionar a nova licença e salvar as configurações da conta novamente, a conta do recurso talvez não funcione mais como esperado. Se isso acontecer, recomendamos que você crie uma nova conta de recurso para a licença de usuário virtual e remova a conta de recurso quebrada.

## <a name="skype-for-business-server-2019"></a>Skype for Business Server 2019

Para contas de recursos hospedadas no Skype for Business Server 2019 que podem ser usadas com filas de chamadas em nuvem e atendedores automáticos na nuvem, consulte [planejar filas de chamadas na](/SkypeforBusiness/hybrid/plan-call-queue) nuvem ou reportar [atendedores automáticos da nuvem](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant). As implementações híbridas (números hospedados no roteamento direto) são configuradas usando o cmdlet [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint) em um servidor local do Skype for Business Server 2019.

As IDs de aplicativo que você precisa usar durante a criação das instâncias do aplicativo são:

- **Atendedor automático:** ce933385-9390-45d1-9512-c8d228074e07
- **Fila de chamadas:** 11cd3e2e-fccb-42AD-ad00-878b93575e07

> [!NOTE]
> Se quiser que a fila de chamadas ou o atendedor automático seja pesquisável pelos usuários do Skype for Business Server 2019, você deve criar suas contas de recursos no Skype for Business Server 2019, pois as contas de recursos online não são sincronizadas com o Active Directory. Quando os registros SRV DNS para sipfederationtls são resolvidos para o Skype for Business Server 2019, as contas de recursos **devem** ser criadas no Skype for business Server 2019 usando o Shell de gerenciamento SfB e sincronizadas com o Azure AD.

Para implementações híbridas com o Skype for Business Server:

   [Atendedores automáticos do plano da nuvem](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)
  
   [Planejar filas de chamadas da nuvem](/SkypeforBusiness/hybrid/plan-call-queue)
   
   [Configurar contas de recurso local](/SkypeForBusiness/hybrid/configure-onprem-ra)


## <a name="delete-a-resource-account"></a>Excluir uma conta de recurso

Certifique-se de dissociar o número de telefone da conta do recurso antes de excluí-lo para evitar que o número do seu serviço fique preso no modo pendente.

Depois de fazer isso, você pode excluir a conta do recurso no centro de administração do Microsoft 365, na guia usuários.

Para desassociar um número de telefone de roteamento direto da conta do recurso, use o seguinte cmdlet:

```powershell
Set-CsOnlineApplicationInstance -Identity  <Resource Account oid> -OnpremPhoneNumber ""
```
