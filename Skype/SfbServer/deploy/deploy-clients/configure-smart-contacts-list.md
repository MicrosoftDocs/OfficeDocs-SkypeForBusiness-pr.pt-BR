---
title: Configurar a lista de contatos inteligentes nos clientes do Skype for Business
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
description: 'Resumo: saiba como ativar o recurso da lista de contatos inteligentes no cliente Skype for Business.'
ms.openlocfilehash: 9db4e6616aa4c11be3ad2f9ee1cd92a0587b4e51
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768864"
---
# <a name="configure-smart-contacts-list-in-skype-for-business-clients"></a>Configurar a lista de contatos inteligentes nos clientes do Skype for Business

**Resumo:** Saiba como ativar o recurso da lista de contatos inteligentes no cliente Skype for Business.

O recurso de lista inteligente de contatos permite a população automática das listas de contatos para seus usuários finais. Depois de usar o Skype for Business, os usuários verão automaticamente o seu gerente e outras pessoas da equipe. Esse recurso está ativado por padrão para os usuários do Office 365, mas você deve habilitar explicitamente esse recurso para seus usuários locais definindo a configuração de política do cliente.

Lembre-se do seguinte ao configurar esse recurso:

- Os usuários, até 13, são adicionados automaticamente à lista de contatos inteligentes na seguinte ordem:

  1. Gerente

  2. Direciona em ordem alfabética

  3. Pares na ordem alfabética

- Na primeira vez que um usuário fizer o logon, um novo grupo, denominado Meu Grupo, será criado. O grupo é automaticamente preenchido com pessoas na relação do grupo de anúncios do usuário com base no alias do usuário preenchido no campo gerente. Observe que as alterações na associação do grupo AD não provocam atualizações em Meu Grupo após ter sido inicialmente preenchido. Se um usuário excluir um contato ou grupo, nenhum contato ou grupo será recriado. 

- Se a auto marcação estiver ativada, os contatos na lista serão marcados para as alterações de presença. A auto marcação é ativada por padrão, mas você pode optar por desativá-la. 

- Todos os novos usuários no grupo serão informados que foram adicionados à lista de contatos. Os usuários podem adicionar manualmente novos membros ao Meu Grupo ou a outros grupos da sua escolha.

- Esse recurso funciona somente para os usuários que estiverem entrando pela primeira vez. Se um usuário tiver feito o logon anteriormente de qualquer dispositivo -- incluindo, por exemplo, qualquer dispositivo móvel ou de um Mac -- o recurso não estará habilitado para esse usuário.

## <a name="configure-smart-contacts-list"></a>Configurar lista de contatos Inteligente

Para habilitar o recurso de lista de contatos Inteligente para seus usuários, será necessário executar as seguintes etapas: 

- Crie uma nova entrada CsClientPolicy e adicione-a à política de cliente global. 

- Certifique-se de que Pesquisa da Agenda está configurada somente para Pesquisa na Web.

### <a name="create-a-policy-entry-to-enable-smart-contacts-list"></a>Criar uma entrada de política para habilitar a lista de contatos Inteligente

Para criar uma entrada de política para habilitar o recurso da lista de contatos inteligentes, use o cmdlet [New-CsClientPolicyEntry](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) com a opção EnableClientAutoPopulateWithTeam da seguinte maneira:

```powershell
$x=New-CsClientPolicyEntry -Name EnableClientAutoPopulateWithTeam -Value $True
```

Em seguida, use o cmdlet [set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) para gravar as alterações na política global da seguinte maneira:

```powershell
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

Como opção, é possível criar uma política para desativar a marcação automática da seguinte maneira:

```powershell
$x=New-CsClientPolicyEntry -Name TagContactsInClientAutoPopulatedGroup -Value $False
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

Você também deve definir o parâmetro AddressBookAvailability para a política correspondente ao WebSearchOnly. Para obter mais informações, consulte [set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps). 

### <a name="troubleshoot"></a>Solução de problemas

Se a Lista de contatos Inteligente não está funcionando conforme o esperado, verifique o seguinte:

- Validar a configuração. 

- Confirme se as informações da organização AD foram preenchidas.

- Coletar logs do cliente Skype for Business em um novo usuário para análise adicional.

- Confirme se a interface do usuário do cliente Skype for Business não está exibindo uma mensagem informando que não consegue se conectar ao catálogo de endereços. Para confirmar a conectividade do catálogo de endereços, realize uma pesquisa de um usuário na barra de pesquisa do cliente Skype for Business.

- Os problemas de replicação do AD DS podem fazer com que os contatos sejam desresolvidos quando um usuário entrar pela primeira vez no Skype for Business.


