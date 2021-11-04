---
title: Criar configurações de reunião em Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 6d8f9ff8-2a04-4175-9bf0-1ec5d78fd015
description: 'Resumo: saiba como criar configurações de reunião em Skype for Business Server.'
ms.openlocfilehash: 03a9194a5b4015d9434641e7946b66c57ff4df77
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60747147"
---
# <a name="create-meeting-configuration-settings-in-skype-for-business-server"></a>Criar configurações de reunião em Skype for Business Server
 
**Resumo:** Saiba como criar configurações de reunião em Skype for Business Server.
  
Você pode criar definições de configuração de reunião usando Skype for Business Server Painel de Controle ou usando Skype for Business Server Shell de Gerenciamento.
  
## <a name="create-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Criar configurações de reunião usando Skype for Business Server Painel de Controle

1. Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.
    
2.  Abra Skype for Business Server Painel de Controle.
    
3. Na barra de navegação esquerda, clique **em Conferência** e em **Configuração de Reunião.**
    
4. Na página **Configuração de reunião**, clique em **Novo** e siga um destes procedimentos:
    
    - Para criar uma política a nível local, clique em **Configuração local**. No campo de pesquisa **Selecionar um local**, digite todo ou parte do nome do local para o qual você deseja definir as configurações de participação de reunião. Na lista resultante de locais, clique no local desejado e em **OK**.
    
    - Para criar uma política a nível de pool, clique em **Configuração do pool**. No campo de pesquisa **Selecionar um serviço**, digite todo ou parte do nome do serviço do pool para o qual você deseja definir as configurações de participação de reunião. Na lista resultante de serviços, clique no pool desejado e em **OK**.
    
5. Para direcionar os participantes que ligam por um PSTN através do lobby, desmarque a caixa de seleção **Os chamadores PSTN ignoram o lobby**. Por padrão, os participantes discando pelo PSTN vão diretamente para a reunião.
    
6. Para configurar quem pode ser um apresentador na reunião, em **Designar como apresentador**, faça um dos seguintes:
    
   - Para não permitir que qualquer pessoa além do organizador seja o apresentador, clique em **Nenhum**.
    
   - Para permitir que apenas participantes membros da sua organização sejam apresentadores, clique em **Empresa**. Esta é a configuração padrão.
    
   - Para permitir qualquer participante ser o apresentador, clique em **Todos**.
    
7. Para que o organizador selecione um tipo de conferência ao programar uma reunião, desmarque a caixa de seleção **Tipo de conferência atribuída por padrão**. Por padrão, o tipo de conferência é atribuído automaticamente.
    
8. Para evitar que usuários anônimos (não autenticados) sejam aceitos automaticamente, desmarque a caixa de seleção **Aceitar usuários anônimos por padrão**. Por padrão, os usuários anônimos são aceitos automaticamente nas reuniões.
    
9. Para personalizar o convite da reunião enviado para os participantes, faça o seguinte. Observe que o comprimento máximo das URLs e o texto do rodapé padrão é de 1KB. Exceto para a **URL de ajuda**, se você não especificar um valor para as personalizações, não serão incluídas na reunião. Se você não incluir uma URL de ajuda personalizada, a URL de ajuda padrão para Skype for Business será exibida no convite. 
    
   - Para personalizar o logotipo exibido no convite da reunião, em **URL do logotipo**, insira o local do logotipo. O logotipo deve ser uma imagem GIF ou JPG com um tamanho de 188 por 30 pixels. 
    
   - Para personalizar o texto de ajuda exibido no convite da reunião, na **URL de ajuda**, insira o local do texto de ajuda.
    
   - Para personalizar o texto legal exibido no convite da reunião, na **URL do texto legal**, insira o local do logotipo.
    
   - Para personalizar o texto do rodapé exibido no convite da reunião, em **Texto do rodapé personalizado**, insira o texto.
    
10. Clique em **Confirmar**.
    
## <a name="create-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Criar configurações de reunião usando Skype for Business Server Shell de Gerenciamento

Para criar configurações de reunião, use o cmdlet **New-CsMeetingConfiguration.**
  
O comando a seguir cria um novo conjunto de configurações de reunião para o site redmond:
  
```PowerShell
New-CsMeetingConfiguration -Identity "site:Redmond"
```

Como não há parâmetros (além do parâmetro obrigatório Identity) onde especificado no comando anterior, as novas definições de configuração de reunião usarão os valores padrões para todas as suas propriedades.
  
Para criar configurações que usam valores de propriedades diferentes, basta incluir o parâmetro e o valor de parâmetro adequados. Por exemplo, para criar um conjunto de reuniões de configuração da reunião que, por padrão, permite todos em uma reunião serem apresentadores a usarem um comando como este:
  
```PowerShell
New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

Vários valores de propriedade podem ser definidos incluindo vários parâmetros. Por exemplo, o comando a seguir reconhece todos em uma reunião como apresentador e também força os usuários PSTN a aguardar no lobby até que sejam formalmente admitidos na reunião:
  
```PowerShell
New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone" -PSTNUCallersBypassLobby $True
```

Para obter mais informações, incluindo uma lista completa de parâmetros, consulte [New-CsMeetingConfiguration](/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps).
