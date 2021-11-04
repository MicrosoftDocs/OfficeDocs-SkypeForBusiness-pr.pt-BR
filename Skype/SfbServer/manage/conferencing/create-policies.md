---
title: Criar políticas de conferência em Skype for Business Server
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
ms.assetid: 8c685326-8356-4075-bf95-32324b16ef81
description: 'Resumo: saiba como criar políticas de conferência em Skype for Business Server.'
ms.openlocfilehash: 1b90a081470cd2df1182bc32d0558a86f860b36a
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60766599"
---
# <a name="create-conferencing-policies-in-skype-for-business-server"></a>Criar políticas de conferência em Skype for Business Server
 
**Resumo:** Saiba como criar políticas de conferência em Skype for Business Server.
  
Você pode criar políticas de conferência usando Skype for Business Server Painel de Controle ou usando Skype for Business Server Shell de Gerenciamento.
  
## <a name="create-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Criar políticas de conferência usando Skype for Business Server Painel de Controle

1. Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.
    
2. Abra Skype for Business Server Painel de Controle.
    
3. Na barra de navegação esquerda, clique **em Conferência** e em Política **de Conferência.**
    
4. Clique em **Nova** e execute um dos seguintes procedimentos:
    
   - Para criar uma política de nível de usuário, clique em **Política de usuário**. Em **Nova Política de Conferências**, em **Nome**, digite um nome descritivo para a política.
    
   - Para criar uma política de nível de site, clique em **Política de site**. No campo de pesquisa **Selecione um Site**, digite todo ou parte do nome do site para o qual deseja criar uma política. Na lista de sites, clique no site que deseja e em **OK**.
    
     > [!NOTE]
     > O nome do site se torna o nome da política de conferência; ele não pode ser alterado. 
  
5. Em **Descrição**, digite uma descrição para a política.
    
6. Sob **Política do Organizador**, em **Tamanho máximo de reuniões**, digite o número máximo de usuários que deseja permitir em uma reunião. Por padrão, o tamanho máximo de reuniões é 250.
    
7. Para impedir que usuários convidem usuários anônimos para a reunião, desmarque a caixa de seleção **Permitir que participantes convidem usuários anônimos**. Os usuários anônimos são usuários que não têm credenciais nos Serviços de Domínio active Directory da sua organização e que, portanto, não são autenticados. Por padrão, os usuários podem convidar usuários anônimos para as reuniões.
    
8. Em **Gravação**, execute um dos seguintes procedimentos:
    
   - Para evitar que os participantes gravem reuniões, clique em **Nenhum**. Esta é a configuração padrão.
    
   - Para permitir que os participantes gravem reuniões, clique em **Habilitar gravação**.
    
9. Para permitir que os participantes externos gravem as reuniões, marque a caixa de seleção **Permitir que participantes anônimos e federados façam gravações**. O padrão é evitar que participantes externos gravem reuniões.
    
10. Em **Áudio/vídeo**, execute um dos seguintes procedimentos:
    
    - Para impedir o uso de áudio e vídeo, clique em **Nenhum**.
    
    - Para permitir o uso de áudio, mas não de vídeo, clique em **Habilitar áudio IP**.
    
    - Para permitir o uso de áudio e vídeo, clique em **Habilitar áudio/vídeo IP**. Esta é a configuração padrão.
    
11. Se você escolher permitir o uso de áudio em **Áudio/vídeo**, faça o seguinte:
    
    - Para impedir que usuários participem da reunião de forma discada, desmarque a caixa de seleção **Habilitar conferência discada PSTN**. Por padrão, os usuários podem participar de forma discada de reuniões usando PSTN.
    
    - Se você permitir que os usuários participem de forma discada das reuniões e deseja permitir que usuários não autenticados (anônimos) participem de uma reunião usando uma telefonia discada, marque a caixa de seleção **Permitir que participantes anônimos façam chamadas**. Com a telefonia discada, o servidor de conferência chama o usuário e o usuário atende ao telefone para participar da reunião. Por padrão, usuários anônimos não podem participar de uma reunião usando a telefonia discada.
    
12. Se você optou por permitir o uso de vídeo em **Áudio/vídeo,** verifique **Permitir vários fluxos de vídeo.**
    
13. Em **Colaboração de dados**, execute um dos seguintes procedimentos:
    
    - Para impedir a colaboração de dados, clique em **Nenhum**.
    
    - Para permitir a colaboração de dados, clique em **Habilitar colaboração de dados**. Esta é a configuração padrão.
    
14. Se você escolher permitir a colaboração de dados em **Colaboração de dados**, faça o seguinte:
    
    - Para impedir os downloads externos, desmarque a caixa de seleção **Permitir que participantes anônimos e federados baixem conteúdo**. Por padrão, os usuários externos podem baixar conteúdo.
    
    - Para impedir as transferências de arquivo, desmarque a caixa de seleção **Permitir que participantes transfiram arquivos**. Por padrão, os usuários podem transferir arquivos.
    
    - Para impedir o uso de anotações, desmarque a caixa de seleção **Habilitar anotações**. Para o uso de anotações em apresentações PowerPoint compartilhadas, desinformar as anotações **Habilitar PowerPoint.** Por padrão, as anotações são permitidas.
    
    - Para impedir o uso de pools, desmarque a caixa de seleção **Habilitar pools**. Por padrão, os pools são permitidos.
    
15. Em **Compartilhamento de aplicativo**, execute um dos seguintes procedimentos:
    
    - Para impedir o uso do compartilhamento de aplicativos, clique em **Desabilitar o compartilhamento de aplicativos**.
    
    - Para permitir o uso do compartilhamento de aplicativos, clique em **Habilitar o compartilhamento de aplicativos**. Esta é a configuração padrão.
    
16. Se você escolher permitir o compartilhamento de aplicativos no **Compartilhamento de aplicativos**, faça o seguinte:
    
    - Para impedir que os participantes da reunião tomem o controle do compartilhamento de aplicativos, desmarque a caixa de seleção **Permitir que os participantes tomem o controle**. Por padrão, os participantes podem tomar o controle do compartilhamento de aplicativos.
    
    - Se você escolher permitir que os participantes da reunião tomem o controle do compartilhamento de arquivos, marque a caixa de seleção **Permitir que participantes federados e anônimos tomem o controle** para permitir que usuários externos tomem o controle do compartilhamento de aplicativos. Por padrão, os usuários externos não podem tomar controle do compartilhamento de aplicativos.
    
17. Em **Política do participante**, execute um dos seguintes procedimentos:
    
    - Para impedir o compartilhamento de aplicativos e o compartilhamento da área de trabalho, clique em **Desabilitar o compartilhamento de aplicativos e da área de trabalho**.
    
    - Para permitir o compartilhamento de aplicativos, mas não o compartilhamento da área de trabalho, clique em **Habilitar o compartilhamento de aplicativos**.
    
    - Para permitir o compartilhamento de aplicativos e da área de trabalho, clique em **Habilitar o compartilhamento de aplicativos e da área de trabalho**. Esta é a configuração padrão.
    
18. Para impedir as transferências de arquivo ponto a ponto, desmarque a caixa de seleção **Habilitar a transferência de arquivo ponto a ponto**. Por padrão, as transferências de arquivo ponto a ponto são permitidas.
    
19. Para permitir a gravação ponto a ponto, marque a caixa de seleção **Habilitar a gravação ponto a ponto**. Por padrão, a gravação ponto a ponto não é permitida.
    
20. Para permitir que os participantes participem de vários fluxos de vídeo, marque a caixa de seleção Habilitar participantes para ingressar com vários **fluxos de** vídeo. Por padrão, vários fluxos de vídeo são permitidos.
    
21. Clique em **Confirmar**.
    
## <a name="create-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Criar políticas de conferência usando o Shell de Gerenciamento Skype for Business Server Gerenciamento

Para criar políticas de conferência, use o cmdlet **New-CsConferencingPolicy.**
  
O exemplo a seguir cria uma nova política de conferência com Identity SalesConferencingPolicy. Esta política usará todos os valores padrão para uma política de conferência, exceto uma: MaxMeetingSize. Neste exemplo, o tamanho máximo de uma reunião será definido como 50 em vez do valor padrão de 250:
  
```PowerShell
New-CsConferencingPolicy -Identity SalesConferencingPolicy -MaxMeetingSize 50
```

Para obter mais informações, incluindo uma descrição de sintaxe completa e uma lista de parâmetros, consulte [New-CsConferencingPolicy](/powershell/module/skype/new-csconferencingpolicy?view=skype-ps).
