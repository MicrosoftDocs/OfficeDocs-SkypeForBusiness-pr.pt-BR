---
title: Configurar lista de contatos Inteligente no Skype for Business Server
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.date: 10/20/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4eecb5f7-3ef7-4582-a6cb-9f4aa068338d
description: Leia este tópico para aprender como ativar o recurso de lista inteligente de contatos no cliente do Skype for Business.
ms.openlocfilehash: f5b5b8f7baa0ce848765a0f2b62aabb118ecb224
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-smart-contacts-list-in-skype-for-business-server"></a>Configurar lista de contatos Inteligente no Skype for Business Server
 
Leia este tópico para aprender como ativar o recurso de lista inteligente de contatos no cliente do Skype for Business.
  
O recurso de lista inteligente de contatos permite a população automática das listas de contatos para seus usuários finais. Depois de usar pela primeira vez o , os usuários automaticamente verão seus gerentes e outras pessoas de sua equipe. Este recurso está ativado por padrão para usuários do , mas você deve explicitamente habilitar esse recurso para seus usuários locais definindo a configuração de política do cliente.
  
Lembre-se do seguinte ao configurar esse recurso:
  
- Usuários, até 13, são automaticamente adicionados à lista de contatos Inteligente na ordem a seguir:
    
  1. Gerente
    
  2. Direciona em ordem alfabética
    
  3. Pares na ordem alfabética
    
- Na primeira vez que um usuário fizer o logon, um novo grupo, denominado Meu Grupo, será criado. O grupo é automaticamente preenchido com pessoas do relacionamento de grupo AD do usuário com base no alias do usuário preenchido no campo Gerenciador. Observe que as alterações na associação do grupo AD não provocam atualizações em Meu Grupo após ter sido inicialmente preenchido. Se um usuário excluir um contato ou grupo, nenhum contato ou grupo será recriado. 
    
- Se a auto marcação estiver ativada, os contatos na lista serão marcados para as alterações de presença. A auto marcação é ativada por padrão, mas você pode optar por desativá-la. 
    
- Todos os novos usuários no grupo serão informados que foram adicionados à lista de contatos. Os usuários podem adicionar manualmente novos membros ao Meu Grupo ou a outros grupos da sua escolha.
    
- Esse recurso funciona somente para os usuários que estiverem entrando pela primeira vez. Se um usuário tiver feito o logon anteriormente de qualquer dispositivo -- incluindo, por exemplo, qualquer dispositivo móvel ou de um Mac -- o recurso não estará habilitado para esse usuário.
    
## <a name="configure-smart-contacts-list"></a>Configurar lista de contatos Inteligente

Para habilitar o recurso de lista de contatos Inteligente para seus usuários, será necessário executar as seguintes etapas: 
  
- Criar uma nova entrada CsClientPolicy e adicioná-la à política global do cliente. 
    
- Certifique-se de que Pesquisa da Agenda está configurada somente para Pesquisa na Web.
    
### <a name="create-a-policy-entry-to-enable-smart-contacts-list"></a>Criar uma entrada de política para habilitar a lista de contatos Inteligente

Para criar uma entrada de política para habilitar o recurso de lista de contatos Inteligente, use o cmdlet [](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) com a opção EnableClientAutoPopulateWithTeam da seguinte maneira:
  
```
$x=New-CsClientPolicyEntry -Name EnableClientAutoPopulateWithTeam -Value $True
```

Em seguida, use o cmdlet [](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps), para gravar as alterações na política global como indicado a seguir:
  
```
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

Como opção, é possível criar uma política para desativar a marcação automática da seguinte maneira:
  
```
$x=New-CsClientPolicyEntry -Name TagContactsInClientAutoPopulatedGroup -Value $False
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}

```

Você também deve definir o parâmetro AddressBookAvailability para a política correspondente ao WebSearchOnly. Para obter mais informações, veja [](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps). 
  
### <a name="troubleshoot"></a>Solução de problemas

Se a Lista de contatos Inteligente não está funcionando conforme o esperado, verifique o seguinte:
  
- Validar a configuração. 
    
- Confirme se as informações da organização AD foram preenchidas.
    
- Colete os logs do cliente  em um novo usuário para análise posterior.
    
- Confirme se a UI do cliente  não está exibindo uma mensagem que não pode se conectar à Agenda. Para confirmar a conectividade da Agenda, execute uma pesquisa para um usuário na barra de pesquisa do cliente .
    
- Se houver problemas de conexão com a Agenda, use STrace para coletar rastreamentos HTTPS e HTTPReplay para analisar os rastreamentos coletados. Para obter mais informações, consulte a [publicação de um blog relacionadohttps://blogs.msdn.microsoft.com/canberrapfe/2012/06/04/have-you-ever-wondered-what-web-service-urls-are-used-by-the-lync-client-strace-is-your-tool/](https://blogs.msdn.microsoft.com/canberrapfe/2012/06/04/have-you-ever-wondered-what-web-service-urls-are-used-by-the-lync-client-strace-is-your-tool/).
    
- A replicação AD DS pode fazer com que os contatos fiquem não-resolvidos quando um usuário entra pela primeira vez no .
    

