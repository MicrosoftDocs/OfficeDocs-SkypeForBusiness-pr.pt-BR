---
title: "Gerenciamento do acesso de usuários ao Microsoft Teams"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: ritikag
description: "Saiba como habilitar ou desabilitar o acesso em nível de usuário na base por usuário."
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: dd2c7490c837e34e242feed295e63a7ebac11dc6
ms.sourcegitcommit: 85105cb4e42ae8eb6e7e76eaf6d4dd5b9568cf41
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2018
---
<a name="manage-user-access-to-microsoft-teams"></a>Gerenciamento do acesso de usuários ao Microsoft Teams
=====================================

Em nível de usuário, o acesso ao Microsoft Teams pode ser habilitado ou desabilitado em uma base por usuário, com a atribuição ou remoção da licença do produto Microsoft Teams.

No momento, não há opções de políticas, além da licença, para tornar o Microsoft Teams, ou um subconjunto de recursos do Microsoft Teams, habilitado ou desabilitado para usuários individualmente.



> [!NOTE]
>A Microsoft recomenda que o Microsoft Teams seja habilitado para todos os usuários da empresa, para que as equipes possam ser formadas naturalmente para os projetos e outras iniciativas dinâmicas. Mesmo que você esteja decidindo por um piloto, ainda pode ser útil manter o Microsoft Teams habilitado para todos os usuários, mas direcionar as comunicações apenas para o grupo piloto de usuários.

As licenças em nível de usuário do Microsoft Teams são gerenciadas diretamente das interfaces de gerenciamento de usuários do Centro de Administração do Office 365. Um administrador pode atribuir licenças a novos usuários quando novas contas de usuário forem criadas ou a usuários com contas existentes. O administrador precisa ter privilégios do Administrador Global do Office 365 ou Administrador de Gerenciamento de Usuários para administrar as licenças do Microsoft Teams.

Quando o SKU de uma licença, como E3 ou E5, for atribuído a um usuário, a licença do Microsoft Teams é atribuída automaticamente e o usuário fica habilitado para o Microsoft Teams. Os administradores podem ter um controle mais detalhado sobre todos os serviços e licenças do Office 365, e a licença do Microsoft Teams para um usuário específico ou um grupo de usuários pode ser habilitada ou desabilitada.

![Captura de tela da seção de licenças de produto no centro de administração do Office 365.](media/Manage_user_access_to_Microsoft_Teams_image2.png) 

A licença do Microsoft Teams de um usuário pode ser desabilitada a qualquer momento. Após a licença ser desabilitada, o acesso do usuário ao Microsoft Teams será impedido e ele não poderá mais visualizar o Microsoft Teams na página inicial nem no inicializador do aplicativo Office 365.

![Captura de tela da seção de licenças de produto no centro de administração do Office 365, mostrando o Microsoft Teams selecionado.](media/Manage_user_access_to_Microsoft_Teams_image4.png)

Além de usar o Centro de Administração do Office 365, os administradores do Office 365 também podem usar o Office 365 PowerShell para atribuir e remover licenças. Para atribuir uma licença a um usuário, use a seguinte sintaxe:

```
Set-MsolUserLicense -UserPrincipalName "\<Account\>" -AddLicenses "\<AccountSkuId\>"
```

O exemplo a seguir atribui uma licença a partir do plano de licença litwareinc:ENTERPRISEPACK (Office 365 Enterprise E3) para o usuário não licenciado belindan@litwareinc.com.

```
Set-MsolUserLicense -UserPrincipalName "belindan@litwareinc.com" -AddLicenses "litwareinc:ENTERPRISEPACK"
```

Para obter mais exemplos e detalhes, veja [Atribuir licenças a contas de usuários do PowerShell do Office 365](https://go.microsoft.com/fwlink/?linkid=855755).

Para remover a licença de uma conta de usuário existente, use a seguinte sintaxe:

```
Set-MsolUserLicense -UserPrincipalName \<Account\> -RemoveLicenses "\<AccountSkuId1\>", "\<AccountSkuId2\>"
```

O exemplo a seguir remove a licença a partir do plano de licença litwareinc:ENTERPRISEPACK (Office 365 Enterprise E3) da conta de usuário BelindaN@litwareinc.com.

```
Set-MsolUserLicense -UserPrincipalName belindan@litwareinc.com -RemoveLicenses "litwareinc:ENTERPRISEPACK"
```

Para obter mais exemplos e detalhes, veja [Remover licenças de contas de usuários do PowerShell do Office 365](https://go.microsoft.com/fwlink/?linkid=855756).

| | | |
|---------|---------|---------|
|![Ícone de ponto de decisão.](media/Manage_user_access_to_Microsoft_Teams_image5.png)     |Ponto de decisão         |<ul><li>Qual é o plano de integração do Microsoft Teams na sua empresa?  (Piloto ou Aberto)</li></ul>         |
|![Ícone de próximos passos.](media/Manage_user_access_to_Microsoft_Teams_image6.png)     |Próximos passos         |<ul><li>Se for iniciar via piloto fechado, decida se deseja fazê-lo através de licenciamento ou comunicação direcionada.</li><li>Dependendo da decisão, tome medidas para se certificar de que apenas os usuários do Piloto tenham permissão para acessar o Microsoft Teams (se necessário).</li><li>Documente as diretrizes de acordo com as quais os usuários terão (ou não) acesso ao Microsoft Teams.</li></ul>         |
