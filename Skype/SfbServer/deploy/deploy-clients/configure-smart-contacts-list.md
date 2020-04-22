---
title: Configurar a lista de contatos inteligente nos clientes do Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4eecb5f7-3ef7-4582-a6cb-9f4aa068338d
description: 'Resumo: saiba como ativar o recurso de lista de contatos inteligentes no cliente Skype for Business.'
ms.openlocfilehash: d99008cde28b834f77a2935ffd7882162aa05e95
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43776686"
---
# <a name="configure-smart-contacts-list-in-skype-for-business-clients"></a>Configurar a lista de contatos inteligente nos clientes do Skype for Business

**Resumo:** Saiba como ativar o recurso de lista de contatos inteligente no cliente Skype for Business.

O recurso de lista de contatos inteligente permite o preenchimento automático de listas de contatos para seus usuários finais. Usando o Skype for Business pela primeira vez, seus usuários verão automaticamente o gerente e outras pessoas de sua equipe. Este recurso está ativado por padrão para os usuários do Microsoft 365 e do Office 365, mas você deve habilitar explicitamente esse recurso para os usuários locais, definindo a configuração de política do cliente.

Tenha em mente o seguinte ao configurar esse recurso:

- Os usuários, até 13, são automaticamente adicionados à lista de contatos inteligentes na seguinte ordem:

  1. Gerente

  2. Direciona em ordem alfabética

  3. Pares em ordem alfabética

- Na primeira vez que um usuário faz logon, um novo grupo, chamado My Group, é criado. O grupo é preenchido automaticamente com pessoas na relação de grupo do AD do usuário com base no alias de usuário preenchido no campo gerente. Observe que as alterações feitas na associação do grupo do AD não causam atualizações para o meu grupo depois que ele é inicialmente preenchido. Se um usuário excluir um contato ou grupo, nem o contato nem o grupo serão recriados. 

- Se a marcação automática estiver ativada, os contatos na lista serão marcados para alterações de presença. A marcação automática é ativada por padrão, mas você pode optar por desativá-la. 

- Todos os novos usuários no grupo serão informados de que foram adicionados à lista de contatos. Os usuários podem adicionar manualmente novos membros ao meu grupo ou a outros grupos de sua escolha.

- Esse recurso funciona somente para usuários que estão entrando pela primeira vez. Se um usuário tiver se conectado anteriormente de qualquer dispositivo, incluindo, por exemplo, qualquer dispositivo móvel ou um Mac--o recurso não está habilitado para esse usuário.

## <a name="configure-smart-contacts-list"></a>Configurar a lista de contatos inteligente

Para habilitar o recurso de lista de contatos inteligentes para seus usuários, será necessário executar as seguintes etapas: 

- Crie uma nova entrada de CsClientPolicy e adicione-a à política de cliente global. 

- Verifique se a pesquisa do catálogo de endereços está configurada somente para pesquisa na Web.

### <a name="create-a-policy-entry-to-enable-smart-contacts-list"></a>Criar uma entrada de política para habilitar a lista de contatos inteligente

Para criar uma entrada de política para habilitar o recurso de lista de contatos inteligente, use o cmdlet [New-CsClientPolicyEntry](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) com a opção EnableClientAutoPopulateWithTeam da seguinte maneira:

```powershell
$x=New-CsClientPolicyEntry -Name EnableClientAutoPopulateWithTeam -Value $True
```

Em seguida, use o cmdlet [set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) para gravar as alterações na política global da seguinte maneira:

```powershell
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

Opcionalmente, você pode criar uma política para desativar a marcação automática da seguinte maneira:

```powershell
$x=New-CsClientPolicyEntry -Name TagContactsInClientAutoPopulatedGroup -Value $False
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

Você também deve definir o parâmetro AddressBookAvailability para a política correspondente como WebSearchOnly. Para obter mais informações, consulte [set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps). 

### <a name="troubleshoot"></a>Solução de problemas

Se a lista de contatos inteligentes não estiver funcionando conforme o esperado, verifique o seguinte:

- Valide a configuração. 

- Confirme se as informações da organização do AD estão preenchidas.

- Coletar logs de cliente do Skype for Business em um novo usuário para análise adicional.

- Confirme que a interface do usuário do cliente Skype for Business não está exibindo uma mensagem informando que não pode se conectar ao catálogo de endereços. Para confirmar a conectividade do catálogo de endereços, execute uma pesquisa para um usuário na barra de pesquisa de cliente do Skype for Business.

- Os problemas de replicação do AD DS podem fazer com que os contatos não sejam resolvidos quando um usuário entra pela primeira vez no Skype for Business.


