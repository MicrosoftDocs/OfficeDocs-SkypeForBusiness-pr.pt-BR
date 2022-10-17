---
title: Gerenciar contas de recursos no Teams
author: CarolynRowe
ms.author: crowe
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
ms.openlocfilehash: ac3eb35894fa765dc44f46fcb489399b06adfa74
ms.sourcegitcommit: cbcf37f395832bed871fe709b87c6eecb1fdfd72
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2022
ms.locfileid: "68584022"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a>Gerenciar contas de recursos no Microsoft Teams

[!INCLUDE [set-up-resource-account-steps](./includes/set-up-resource-account-steps.md)]

## <a name="next-steps"></a>Próximas etapas

Depois de concluir a configuração da conta de recurso e atribuir um número de serviço, se necessário, você estará pronto para usar a conta de recurso com um atendedor automático ou fila de chamadas.

Confira as seguintes referências para saber mais:

- [Atendedor automático de nuvem](create-a-phone-system-auto-attendant.md)
- [Fila de chamadas na nuvem](create-a-phone-system-call-queue.md)

Você pode editar o nome **de exibição** da conta de recurso e **o tipo de conta de** recurso usando a **opção** Editar. Clique **em Salvar** quando terminar.

## <a name="change-an-existing-resource-account-to-use-a-teams-phone-resource-account-license"></a>Alterar uma conta de recurso existente para usar uma licença de Conta de Recurso de Telefone do Teams

Se você decidir alternar as licenças em sua conta de recurso existente de uma licença do **Telefonia do Teams Padrão** para uma licença de conta de recurso do Telefonia do Microsoft Teams, precisará adquirir **a** licença gratuita da Conta de Recurso de Telefone do **Teams** e seguir as etapas nas Centro de administração do Microsoft 365 [mover usuários para uma assinatura diferente](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription).

> [!WARNING]
> Sempre remova uma licença Telefonia do Teams Padrão e atribua a licença **Telefonia do Microsoft Teams conta de** recurso na mesma atividade de licença. Se você remover a licença antiga, salvar as alterações da conta, adicionar a nova licença e salvar as configurações da conta novamente, a conta de recurso poderá não funcionar mais conforme o esperado. Se isso acontecer, recomendamos que você crie uma nova conta de recurso para a licença **Telefonia do Microsoft Teams conta** de recurso e remova a conta de recurso interrompida.

## <a name="skype-for-business-server-2019"></a>Skype for Business Server 2019

Para contas de recursos [hospedados](/SkypeforBusiness/hybrid/plan-call-queue) no Skype for Business Server 2019 que podem ser usadas com filas de chamadas na nuvem e atendedores automáticos de nuvem, consulte Filas de chamadas do Plan Cloud ou atendedores [automáticos do Plan Cloud](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant). Implementações híbridas (números hospedados no Roteamento Direto) são configuradas usando o cmdlet [New-CsHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint) em um servidor Skype for Business Server 2019 local.

As IDs de aplicativo que você precisa usar ao criar as instâncias de aplicativo são:

- **Atendedor Automático:** ce933385-9390-45d1-9512-c8d228074e07
- **Fila de Chamadas:** 11cd3e2e-fcb-42ad-ad00-878b93575e07

> [!NOTE]
> Se você quiser que a fila de chamadas ou o atendedor automático seja pesquisável pelos usuários do Skype For Business Server 2019, crie suas contas de recurso no Skype For Business Server 2019, pois as contas de recursos online não estão sincronizadas com o Active Directory. Quando os registros SRV dns para sipfederationtls são resolvidos para o Skype for Business Server 2019, as contas de  recursos devem ser criadas no Skype For Business Server 2019 usando o shell de Gerenciamento SfB e sincronizadas com o Azure AD.

Para implementações híbridas com Skype for Business Server:

   [Atendedores automáticos do plano da nuvem](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)

   [Planejar filas de chamadas da nuvem](/SkypeforBusiness/hybrid/plan-call-queue)

   [Configurar contas de recursos locais](/SkypeForBusiness/hybrid/configure-onprem-ra)

## <a name="delete-a-resource-account"></a>Excluir uma conta de recurso

Desassocie o número de telefone da conta de recurso antes de excluí-lo, para evitar que o número de serviço seja preso no modo pendente.

Depois de fazer isso, você pode excluir a conta de recurso no Centro de administração do Microsoft 365, na guia Usuários.

Para desassociar um número de telefone de roteamento direto da conta de recurso, use o seguinte cmdlet:

```powershell
Remove-CsPhoneNumberAssignment -Identity <Resource Account Object ID> -PhoneNumber <assigned phone number> -PhoneNumberType DirectRouting
```
