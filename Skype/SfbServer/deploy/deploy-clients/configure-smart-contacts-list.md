---
title: Configurar a lista de contatos Inteligente nos clientes do Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4eecb5f7-3ef7-4582-a6cb-9f4aa068338d
description: 'Resumo: saiba como ativar o recurso Lista de contatos Inteligente no cliente Skype for Business.'
ms.openlocfilehash: d995d2addf8b774ebad9945b3f35f07ddb431855
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805771"
---
# <a name="configure-smart-contacts-list-in-skype-for-business-clients"></a>Configurar a lista de contatos Inteligente nos clientes do Skype for Business

**Resumo:** Saiba como ativar o recurso de lista de contatos Inteligentes no cliente Skype for Business.

O recurso de lista de contatos Inteligente permite a população automática de listas de contatos para seus usuários finais. Ao usar o Skype for Business pela primeira vez, os usuários verão automaticamente o gerente e outras pessoas da equipe. Esse recurso é ativado por padrão para usuários do Microsoft 365 e do Office 365, mas você deve habilitar explicitamente esse recurso para seus usuários locais definindo a configuração de política de cliente.

Lembre-se do seguinte ao configurar esse recurso:

- Os usuários, até 13, são adicionados automaticamente à lista de contatos Inteligente na seguinte ordem:

  1. Manager

  2. Direciona em ordem alfabética

  3. Pares em ordem alfabética

- Na primeira vez que um usuário faz login, um novo grupo, chamado Meu Grupo, é criado. O grupo é preenchido automaticamente com pessoas na relação de grupo do AD do usuário com base no alias do usuário preenchido no campo Gerente. Observe que as alterações na associação de grupo do AD não causam atualizações em Meu Grupo depois que ele é preenchido inicialmente. Se um usuário excluir um contato ou o grupo, nem o contato nem o grupo serão criados outra vez. 

- Se a marcação automática estiver turned on, os contatos na lista serão marcados para alterações de presença. A marcação automática é 2.000 por padrão, mas você pode optar por desativar a marcação. 

- Todos os novos usuários do grupo serão informados de que foram adicionados à lista de contatos. Os usuários podem adicionar manualmente novos membros ao Meu Grupo ou a outros grupos de sua escolha.

- Esse recurso funciona apenas para usuários que estão fazendo logom pela primeira vez. Se um usuário tiver feito o acesso anteriormente em qualquer dispositivo , incluindo, por exemplo, qualquer dispositivo móvel ou um Mac, o recurso não está habilitado para esse usuário.

## <a name="configure-smart-contacts-list"></a>Configurar a lista de contatos Inteligente

Para habilitar o recurso de lista de contatos Inteligente para seus usuários, você precisará executar as seguintes etapas: 

- Crie uma nova entrada CsClientPolicy e adicione-a à política de cliente global. 

- Certifique-se de que a Pesquisa do Livro de Endereços está configurada somente para Pesquisa da Web.

### <a name="create-a-policy-entry-to-enable-smart-contacts-list"></a>Criar uma entrada de política para habilitar a lista de contatos Inteligente

Para criar uma entrada de política para habilitar o recurso de lista de contatos Inteligente, use o cmdlet [New-CsClientPolicyEntry](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) com a opção EnableClientAutoPopulateWithTeam da seguinte forma:

```powershell
$x=New-CsClientPolicyEntry -Name EnableClientAutoPopulateWithTeam -Value $True
```

Em seguida, use o cmdlet [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) para gravar as alterações na política global da seguinte forma:

```powershell
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

Opcionalmente, você pode criar uma política para desativar a marcação automática da seguinte maneira:

```powershell
$x=New-CsClientPolicyEntry -Name TagContactsInClientAutoPopulatedGroup -Value $False
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

Você também deve definir o parâmetro AddressBookAvailability para a política correspondente para WebSearchOnly. Para obter mais informações, [consulte Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps). 

### <a name="troubleshoot"></a>Solução de problemas

Se a lista de contatos Inteligente não estiver funcionando conforme o esperado, verifique o seguinte:

- Valide a configuração. 

- Confirme se as informações da organização do AD estão preenchidas.

- Coletar logs de cliente do Skype for Business em um novo usuário para análise posterior.

- Confirme se a interface do usuário do cliente Skype for Business não está exibindo uma mensagem de que não pode se conectar ao Address Book. Para confirmar a conectividade do Livro de Endereços, execute uma pesquisa para um usuário na barra de pesquisa do cliente Skype for Business.

- Problemas de replicação do AD DS podem fazer com que os contatos não sejam resolvidos quando um usuário entrar pela primeira vez no Skype for Business.


