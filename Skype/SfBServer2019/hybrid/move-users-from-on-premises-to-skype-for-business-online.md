---
title: Mover usuários do local para o Skype for Business Online
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
ms.custom: ''
description: 'Resumo: Saiba como migrar configurações do usuário e movam usuários para Skype para negócios Online.'
ms.openlocfilehash: 9fd51c55be35e55be6ca837ccb72413043283ac7
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "25030746"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a>Mover usuários do local para o Skype for Business Online

**Resumo:** Saiba como migrar configurações do usuário e movam usuários para Skype para negócios Online.

Antes de realmente mover um usuário para o Office 365, primeiro você deve confirmar que as contas de usuário são sincronizadas com a nuvem e atribuí-las uma licença. Para fazer isso, use o Centro de Administração do Office 365.

### <a name="to-confirm-that-an-on-premises-user-account-has-been-synchronized-with-office-365"></a>Para confirmar que uma conta de usuário local foi sincronizada com o Office 365

1. Usando uma conta de administração de locatário, abra o Centro de administração do Office 365 para seu locatário.  Contas de administração de Inquilino devem ser concedidas a ambos o Skype para a função de administrador de negócios e a função de gerenciamento do usuário (ou a função de Administrador Global) executar essa função no Office 365.

2. No painel de navegação à esquerda, clique em **usuários**e, em seguida, clique em **Usuários ativos**.

3. Clique em **Pesquisar um Usuário**e digite o nome do usuário.

4. Confirme que você veja o usuário e se o seu status é **Synched com o Active Directory**.

    Se o usuário ainda não está sincronizado, a próxima sincronização automática deve acontecer no prazo de três horas. Você também pode forçar uma sincronização antes. Para obter mais informações, consulte [Forçar sincronização de diretórios](https://msdn.microsoft.com/en-us/library/azure/jj151771.aspx).

Para atribuir a licença no Office 365, consulte [Atribuir licenças aos usuários no Office 365 para empresas](https://support.office.com/en-us/article/Assign-or-unassign-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc).

## <a name="migrate-user-settings-to-skype-for-business-online"></a>Migrar configurações do usuário para o Skype para negócios Online

Antes de migrar usuários para Skype para Business Online, você deve fazer backup dos dados de usuário associados com as contas a serem movidos. Nem todos os dados de usuário são movidos junto com a conta. Para obter informações, consulte [requisitos de Backup e restauração: dados](https://technet.microsoft.com/library/ecfb8e4d-cb4f-476d-9772-4486bd683c04.aspx).

As configurações do usuário são movidas com a conta do usuário. Algumas configurações locais não são movidas com a conta do usuário.

## <a name="move-pilot-users-to-skype-for-business-online"></a>Mover usuários piloto para Skype para negócios Online

Antes de mover usuários para Skype para Business Online, convém mover alguns usuários piloto para confirmar que o ambiente está configurado corretamente. Será então possível verificar se os recursos e serviços funcionam conforme o esperado antes de tentar mover usuários adicionais.

Para mover um usuário local para seu Skype para locatário Business Online, execute os cmdlets a seguir no Skype do Shell de gerenciamento do servidor de negócios, utilizando as credenciais de administrador para o seu locatário do Microsoft Office 365. Substitua "username@contoso.com" as informações do usuário que você deseja mover.

```
$creds=Get-Credential
```

```
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds
```

## <a name="move-users-to-skype-for-business-online"></a>Mover usuários para o Skype for Business Online

Você pode mover vários usuários usando o cmdlet [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) com o parâmetro - Filter para selecionar os usuários com uma propriedade específica atribuída às contas de usuário, como RegistrarPool. Em seguida, você pode direcionar os usuários retornados para o cmdlet [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser?view=skype-ps) , conforme mostrado no exemplo a seguir:

```
Get-CsUser -Filter {UserProperty -eq "UserPropertyValue"} | Move-CsUser -Target sipfed.online.lync.com -Credential $creds
```

Você também pode usar o parâmetro - OU para recuperar todos os usuários na unidade Organizacional especificada, conforme mostrado no exemplo a seguir:

```
Get-CsUser -OU "cn=hybridusers,cn=contoso.." | Move-CsUser -Target sipfed.online.lync.com -Credentials $creds
```

## <a name="verify-online-user-settings-and-features"></a>Verifique as configurações e os recursos do usuário online

Você pode verificar que o usuário foi movido com sucesso das seguintes formas:

- Exibir o status do usuário no Painel de Controle do Skype for Business Online. O indicador visual para usuários no local e online é diferente.

- Execute o seguinte cmdlet:

  ```
  Get-CsUser -Identity
  ```


