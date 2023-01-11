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
ms.openlocfilehash: 2bc0642f20341b9818b1c407fa0294127ee44d6a
ms.sourcegitcommit: ae687f530d5505b96df7cb7ef4da3a36bd9afd29
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/10/2023
ms.locfileid: "69763572"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a>Gerenciar contas de recursos no Microsoft Teams

[!INCLUDE [set-up-resource-account-steps](./includes/set-up-resource-account-steps.md)]

## <a name="next-steps"></a>Próximas etapas

Depois de concluir a configuração da conta de recurso e atribuir um número de telefone, se necessário, você estará pronto para usar a conta de recurso com um atendente automático ou fila de chamadas.

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

- [Planeje os atendentes automáticos do Cloud](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant).
- [Planejar filas de chamadas na nuvem](/SkypeforBusiness/hybrid/plan-call-queue).
- [Configurar contas de recursos locais](/SkypeForBusiness/hybrid/configure-onprem-ra).

## <a name="delete-a-resource-account"></a>Excluir uma conta de recurso

Certifique-se de dissociar o número de telefone da conta de recurso antes de excluí-lo, para evitar que seu número de telefone fique preso no modo pendente.

Depois de fazer isso, você pode excluir a conta de recurso no Centro de administração do Microsoft 365, na guia **Usuários**.

Para desassociar um número de telefone de Roteamento Direto da conta de recurso, use o seguinte cmdlet:

```powershell
Remove-CsPhoneNumberAssignment -Identity <Resource Account Object ID> -PhoneNumber <assigned phone number> -PhoneNumberType DirectRouting
```

## <a name="hide-resource-accounts-from-teams-users"></a>Ocultar contas de recursos de usuários do Teams

Talvez você queira ocultar determinadas contas de recursos de usuários do Teams. Por exemplo, você pode querer impedir que os usuários do Teams chamem diretamente uma fila de chamadas e ignorem o atendente automático em que as horas de operação estão configuradas.

[As barreiras de informações são usadas](information-barriers-in-teams.md) para ocultar as contas de recurso.  Examine a documentação de barreiras de informações para entender os possíveis impactos antes de prosseguir com as etapas abaixo.

### <a name="required-subscriptions-and-permissions"></a>Assinaturas e permissões necessárias 

Para acessar e usar barreiras de informações, sua organização deve ter uma das seguintes assinaturas ou suplementos: 

-   assinatura Microsoft 365 E5/A5 (versão paga ou de avaliação).
-   assinatura Office 365 E5/A5/A3/A1 (versão paga ou de avaliação).
-   Conformidade Avançada do Office 365 complemento.
-   assinatura Microsoft 365 E3/A3/A1 + o complemento de conformidade Microsoft 365 E5/A5.
- assinatura Microsoft 365 E3/A3/A1 + o complemento Microsoft 365 E5/A5 Insider Risk Management.

> [!NOTE]
> Se você já tiver [Exchange Online](/exchange/address-books/address-book-policies/address-book-policies) políticas de catálogo de endereços configuradas, elas devem ser removidas antes de prosseguir com as etapas abaixo.   
> 
> Todas as etapas abaixo são executadas pelo Administrador Global do Locatário. 
>   
> Essas instruções pressupõem que não há outras barreiras de informações configuradas.

#### <a name="teams-admin-center"></a>Centro de administração do Teams

1. Entre no [centro de administração do Teams](https://go.microsoft.com/fwlink/p/?linkid=2066851).
2. No menu do trilho esquerdo, expanda **o Teams**.
3. Selecione **Configurações do Teams**. 
4. Role para baixo até **Pesquisar pelo nome**.
5. Ative a alternância e salve a alteração.

Para obter mais informações sobre essa opção, consulte [Limitar quem os usuários podem ver ao pesquisar o diretório no Teams](teams-scoped-directory-search.md).

#### <a name="compliance---auditing"></a>Conformidade – Auditoria

1. Entre no [portal de conformidade do Microsoft Purview](https://compliance.microsoft.com/).
2. No painel de navegação esquerdo, selecione **Auditoria**.
3. Se a auditoria for desativada, o seguinte banner será exibido: 
 
     :::image type="content" source="/microsoft-365/media/AuditingBanner.png" alt-text="Captura de tela mostrando o banner de auditoria se a auditoria não estiver habilitada":::
  
4. Selecione **a atividade Iniciar gravação de usuário e administrador**. 

Para obter mais informações sobre auditoria, consulte [Configurar Auditoria (Standard) no Microsoft 365](/microsoft-365/compliance/audit-standard-setup).

#### <a name="segmenting-data"></a>Segmentação de dados

As Contas de Recurso que não devem ser chamadas diretamente precisam ser segmentadas e facilmente identificáveis.  Isso pode ser feito tornando-os membros de um determinado grupo ou por algumas informações exclusivas em seu perfil de usuário, como: 

-   Empresa
-   Nome da entidade de usuário
-   Localização
-   Departamento
-   Local de uso
-   Apelido de email (Alias)
-   Nome do escritório de entrega física (Office)
-   Código postal
-   Endereço proxy (endereço Email)
-   Endereço de rua
-   Endereço de destino (ExternalEmailAddress)
-   Email (WindowsEmailAddress)
-   Descrição

Nas etapas de exemplo abaixo, o `Department` campo será usado. 

Para obter mais informações sobre segmentação de  [usuários, consulte Identificar segmentos](/microsoft-365/compliance/information-barriers-policies).

#### <a name="microsoft-admin-center"></a>Centro de administração da Microsoft

1. Entre no [Centro de Administração Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2024339).
2. No painel de navegação à esquerda, selecione **Usuários Ativos**.
3. Selecione a primeira Conta de Recurso para bloquear chamadas diretas.
4. Selecione **Gerenciar informações de contato** no painel direito.
5. Substitua o conteúdo do `Department` campo por uma palavra ou acrônimo exclusivo que não seja usado como um nome de departamento. Por exemplo, `DNC`.
6. Salve as alterações.
7. Repita para cada Conta de Recurso que precisa ser impedida de receber chamadas diretas.

#### <a name="compliance---information-barriers"></a>Conformidade – Barreiras de informações

1. Entre no [portal de conformidade do Microsoft Purview](https://compliance.microsoft.com/).
2. No painel de navegação esquerdo, selecione **Barreiras** >  de informações **Segmentos**.
3. Selecione **Novo segmento**.
4. Insira um nome para o segmento e selecione **Avançar**. Por exemplo, `Uncallable Resource Accounts`.
5. Selecione **+ Adicionar** e, em seguida, **Departamento**.
6. Insira a palavra ou acrônimo exclusivo usado no centro de administração da Microsoft etapa 5 acima. Por exemplo, `DNC`.
7. Selecione **Avançar** e, em seguida, **Enviar**.
8. Selecione **Novo segmento**.
9. Insira um nome para o segmento e selecione **Avançar**. Por exemplo, `Callable Users`.
10. Selecione **+ Adicionar** e, em seguida, **Departamento**.
11. Selecione **a lista suspensa Igual** e selecione **Não igual a**.
12. Insira a palavra ou acrônimo exclusivo usado no centro de administração da Microsoft etapa 5 acima. Por exemplo, `DNC`.
13. Selecione **Avançar** e, em seguida, **Enviar**. 
14. No painel de navegação esquerdo, selecione **Políticas de barreiras** > **de informações**.
15. Selecione **Criar política**.
16. Insira um nome para a política e selecione **Avançar**. Por exemplo, `Uncallable Resource Accounts`.
17. Selecione **+ Escolher segmento**, adicione o segmento criado na etapa 9 acima e selecione **Avançar**. Por exemplo, `Callable Users`.
18. Selecione **Bloqueado** na lista suspensa **Comunicação e colaboração** .
19. Selecione **+ Escolher segmento**, adicione o segmento criado na etapa 4 acima e selecione **Avançar**. Por exemplo, `Uncallable Resource Accounts`.
20. Defina a política como **Ativar**, selecione **Avançar** e, em seguida, **Enviar**.
21. Selecione **Criar política**.
22. Insira um nome para a política e selecione **Avançar**. Por exemplo, `Callable Users`.
23. Selecione **+ Escolher segmento**, adicione o segmento criado na etapa 4 e selecione **Avançar**.
24. Selecione **Bloqueado** na lista suspensa **Comunicação e colaboração** . 
25. Selecione **+ Escolher segmento**, adicione o segmento criado na etapa 9 acima e selecione **Avançar**.
26. Defina a política como **Ativar**, selecione **Avançar** e, em seguida, **Enviar**.
27. No painel de navegação esquerdo, selecione **Barreiras** >  de informações **Aplicativo de política**.
28. Selecione **Aplicar todas as políticas**.

> [!NOTE]
> Pode levar 30 minutos ou mais para que a política seja aplicada.  
> 
> Depois que o status for concluído, vá para o Cliente do Teams e tente pesquisar as Contas de Recurso que foram bloqueadas. Talvez seja necessário limpar o cache do Teams.  
> 
> Se um usuário do Teams tiver salvo a Conta de Recursos como um contato, ele não poderá mais chamá-la.
