---
title: Gerenciar contas de recursos no Teams
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.reviewer: jastark, wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
- seo-marvel-apr2020
description: Neste artigo, você aprenderá a criar, editar e gerenciar contas de recursos no Microsoft Teams.
ms.openlocfilehash: cde570c23b6d2e6b673f6cc0f49c9905c3b45fd1
ms.sourcegitcommit: 55d2f515f5040b4c083f529d7b818c84d42378a0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/22/2022
ms.locfileid: "69147428"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a>Gerenciar contas de recursos no Microsoft Teams

[!INCLUDE [set-up-resource-account-steps](./includes/set-up-resource-account-steps.md)]

## <a name="next-steps"></a>Próximas etapas

Depois de concluir a configuração da conta de recurso e atribuir um número de serviço, se necessário, você estará pronto para usar a conta de recurso com um atendente automático ou fila de chamadas.

Confira as seguintes referências para saber mais:

- [Assistente automático de nuvem](create-a-phone-system-auto-attendant.md)
- [Fila de chamadas na nuvem](create-a-phone-system-call-queue.md)

Você pode editar a conta **de recurso Nome de exibição** e tipo **de conta de recurso** usando a opção **Editar** . Selecione **Salvar** quando terminar.

## <a name="change-an-existing-resource-account-to-use-a-microsoft-teams-phone-resource-account-license"></a>Alterar uma conta de recurso existente para usar uma licença da Conta de Recurso Telefonia do Microsoft Teams

Para alternar as licenças em sua conta de recurso existente de uma licença **de Telefonia do Teams Padrão** para uma licença **da Conta de Recurso Telefonia do Microsoft Teams**, você precisará adquirir a licença **Telefonia do Microsoft Teams Conta de Recursos** e, em seguida, seguir a etapas no Centro de administração do Microsoft 365 [para Mover usuários para uma assinatura diferente](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription).

> [!WARNING]
> Sempre remova uma licença **de Telefonia do Teams Padrão** e atribua a licença **Telefonia do Microsoft Teams Conta de Recursos** na mesma atividade de licença. Se você remover a licença antiga, salvar as alterações da conta, adicionar a nova licença e salvar as configurações da conta novamente, a conta de recurso poderá não funcionar mais conforme o esperado. Se isso acontecer, recomendamos que você crie uma nova conta de recurso para a **licença Telefonia do Microsoft Teams Conta de Recursos** e remova a conta de recurso quebrada.

## <a name="skype-for-business-server-2019"></a>Skype For Business Server 2019

Para contas de recursos abrigadas no Skype For Business Server 2019 que podem ser usadas com filas de chamadas na nuvem e atendentes automáticos de nuvem, consulte [Filas de chamadas do Plan Cloud](/SkypeforBusiness/hybrid/plan-call-queue) ou [Assistentes automáticos do Plan Cloud](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant). As implementações híbridas (números hospedados no Roteamento Direto) são configuradas usando o cmdlet [New-CsHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint) em um servidor local Skype for Business Server 2019.

As IDs do aplicativo que você precisa usar durante a criação das instâncias de aplicativo são:

- **Atendente Automático:** ce933385-9390-45d1-9512-c8d228074e07
- **Fila de chamadas:** 11cd3e2e-fccb-42ad-ad00-878b93575e07

> [!NOTE]
> Se você quiser que a fila de chamadas ou o atendente automático sejam pesquisados pelos usuários do Skype For Business Server 2019, crie suas contas de recursos no Skype For Business Server 2019, já que as contas de recursos online não são sincronizadas com o Active Directory. Quando os registros DNS SRV para sipfederationtls resolverem Skype for Business Server 2019, as contas de recursos **devem** ser criadas no Skype For Business Server 2019 usando o shell de Gerenciamento de SfB e sincronizadas com Azure AD.

Para implementações híbridas com Skype for Business Server:

   [Atendedores automáticos do plano da nuvem](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)

   [Planejar filas de chamadas da nuvem](/SkypeforBusiness/hybrid/plan-call-queue)

   [Configurar contas de recursos locais](/SkypeForBusiness/hybrid/configure-onprem-ra)

## <a name="delete-a-resource-account"></a>Excluir uma conta de recurso

Certifique-se de dissociar o número de telefone da conta de recurso antes de excluí-lo, para evitar que o número de serviço fique preso no modo pendente.

Depois de fazer isso, você pode excluir a conta de recurso no Centro de administração do Microsoft 365, na guia **Usuários**.

Para desassociar um número de telefone de Roteamento Direto da conta de recurso, use o seguinte cmdlet:

```powershell
Remove-CsPhoneNumberAssignment -Identity <Resource Account Object ID> -PhoneNumber <assigned phone number> -PhoneNumberType DirectRouting
```
