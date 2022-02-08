---
title: Configurar a lista de contatos inteligentes em Skype for Business clientes
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 4eecb5f7-3ef7-4582-a6cb-9f4aa068338d
description: 'Resumo: saiba como ativar o recurso de lista de contatos inteligentes no Skype for Business cliente.'
ms.openlocfilehash: 7c9168b076027dabd7904c1344bd0b83f3d8b8df
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62394373"
---
# <a name="configure-smart-contacts-list-in-skype-for-business-clients"></a>Configurar a lista de contatos inteligentes em Skype for Business clientes

**Resumo:** Saiba como ativar o recurso de lista de contatos inteligentes no Skype for Business cliente.

O recurso de lista de contatos inteligentes permite a população automática de listas de contatos para seus usuários finais. Ao usar o Skype for Business, os usuários verão automaticamente o gerente e outras pessoas em sua equipe. Esse recurso é ativado por padrão para usuários Microsoft 365 e Office 365, mas você deve habilitar explicitamente esse recurso para seus usuários locais configurando a configuração de política do cliente.

Lembre-se do seguinte ao configurar este recurso:

- Os usuários, até 13 anos, são adicionados automaticamente à lista de contatos Inteligentes na seguinte ordem:

  1. Manager

  2. Direciona em ordem alfabética

  3. Pares em ordem alfabética

- Na primeira vez que um usuário faz login, um novo grupo, chamado Meu Grupo, é criado. O grupo é preenchido automaticamente com pessoas na relação de grupo do AD do usuário com base no alias do usuário preenchido no campo Gerenciador. Observe que as alterações na associação ao grupo do AD não causam atualizações para o Meu Grupo depois que ele é preenchido inicialmente. Se um usuário excluir um contato ou o grupo, nem o contato nem o grupo serão re-criados. 

- Se a marcação automática estiver ativas, os contatos na lista serão marcados para alterações de presença. A marcação automática está 100%, mas você pode optar por desativar. 

- Todos os novos usuários do grupo serão informados de que foram adicionados à lista de contatos. Os usuários podem adicionar manualmente novos membros ao Meu Grupo ou a outros grupos de sua escolha.

- Esse recurso funciona apenas para usuários que estão fazendo logor pela primeira vez. Se um usuário tiver conectado anteriormente a partir de qualquer dispositivo, incluindo, por exemplo, qualquer dispositivo móvel ou um Mac, o recurso não está habilitado para esse usuário.

## <a name="configure-smart-contacts-list"></a>Configurar a lista de contatos Inteligente

Para habilitar o recurso de lista de contatos inteligentes para seus usuários, você precisará executar as seguintes etapas: 

- Crie uma nova entrada CsClientPolicy e adicione-a à política de cliente global. 

- Certifique-se de que a Pesquisa do Livro de Endereços está configurada somente para Pesquisa da Web.

### <a name="create-a-policy-entry-to-enable-smart-contacts-list"></a>Criar uma entrada de política para habilitar a lista de contatos inteligentes

Para criar uma entrada de política para habilitar o recurso de lista de contatos inteligentes, use o cmdlet [New-CsClientPolicyEntry](/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) com a opção EnableClientAutoPopulateWithTeam da seguinte forma:

```powershell
$x=New-CsClientPolicyEntry -Name EnableClientAutoPopulateWithTeam -Value $True
```

Em seguida, use o cmdlet [Set-CsClientPolicy](/powershell/module/skype/set-csclientpolicy?view=skype-ps) para gravar as alterações na política global da seguinte forma:

```powershell
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

Opcionalmente, você pode criar uma política para desativar a marcação automática da seguinte maneira:

```powershell
$x=New-CsClientPolicyEntry -Name TagContactsInClientAutoPopulatedGroup -Value $False
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

Você também deve definir o parâmetro AddressBookAvailability para a política correspondente como WebSearchOnly. Para obter mais informações, [consulte Set-CsClientPolicy](/powershell/module/skype/set-csclientpolicy?view=skype-ps). 

### <a name="troubleshoot"></a>Solução de problemas

Se a lista de contatos inteligentes não estiver funcionando conforme o esperado, verifique o seguinte:

- Valide a configuração. 

- Confirme se as informações da organização do AD estão preenchidas.

- Coletar Skype for Business logs de cliente em um novo usuário para análise mais detalhada.

- Confirme se Skype for Business interface do usuário do cliente não está exibindo uma mensagem de que não pode se conectar ao Livro de Endereços. Para confirmar a conectividade do Livro de Endereços, execute uma pesquisa para um usuário na barra de pesquisa Skype for Business cliente.

- Problemas de replicação do AD DS podem fazer com que os contatos não sejam resolvidos quando um usuário entrar pela primeira vez Skype for Business.