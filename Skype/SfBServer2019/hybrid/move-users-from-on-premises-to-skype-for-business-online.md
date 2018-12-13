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
description: Saiba como mover usuários para Skype para negócios Online.
ms.openlocfilehash: 083f2f52fd07439d85d017db9c4b035b8ea326b6
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/13/2018
ms.locfileid: "27243994"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a>Mover usuários do local para o Skype for Business Online

Depois de mover um usuário no local para Skype para Business Online, o usuário interage com Skype para Business Online para sua funcionalidade. Todos os contatos que existiam no local estarão disponíveis na Skype para Business Online e quaisquer reuniões existentes que o usuário organizou para o futuro são atualizadas para para que os links apontam para Skype para negócios Online. Se o usuário estiver habilitado para conferência de áudio, as reuniões também incluirá as coordenadas de discagem.  Para mover usuários de um ambiente local para Skype para Business Online, use o cmdlet Move-CsUser ou o Skype para painel de controle do Business Server, ambos os quais são as ferramentas de local. 

Antes de mover todos os usuários, certifique-se de revisar os [pré-requisitos](move-users-between-on-premises-and-cloud.md#prerequisites) para mover usuários para a nuvem.
 
## <a name="move-users-with-move-csuser"></a>Mover os usuários com Move-CsUser 

Move-CsUser está disponível no Skype local para a janela do PowerShell de Shell de gerenciamento de negócios. Você deve ter privilégios suficientes em ambos o ambiente local, bem como o locatário do Office 365, conforme descrito em [necessárias credenciais administrativas](move-users-between-on-premises-and-cloud.md#required-administrative-credentials). Você pode usar uma única conta que possua privilégios nos dois ambientes, ou você pode iniciar uma Skype no local para a janela do Shell de gerenciamento do servidor de negócios com credenciais no local e usar o `-Credential` parâmetro para especificar as credenciais para um Office 365 conta com a função administrativa do Office 365 necessária.

Para mover um usuário para online usando o Move-CsUser:

- Especifique o usuário mover usando o parâmetro Identity.
- Especificar o - parâmetro de destino com o valor "sipfed.online.lync. <span>com ".
- Se você não tiver uma conta com permissões suficientes em ambos no local e o Office 365, use o parâmetro - credential para fornecer uma conta com permissões suficientes no Office 365.
- Se a conta com permissões no Office 365 não termina em "on.microsoft. <span>com ", e em seguida, você deve especificar o parâmetro - HostedMigrationOverrideUrl, com o valor correto, conforme descrito em [necessárias credenciais administrativas](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).

A seguinte sequência de cmdlet pode ser usada para mover um usuário para Skype para Business Online e assume a credencial do Office 365 é uma conta separada e fornecidos como entrada para o prompt de Get-Credential.

```
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
 
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
```
## <a name="move-users-with-skype-for-business-server-control-panel"></a>Mover os usuários com Skype para painel de controle do servidor de negócios 

1. Abra o Skype para controle de servidor de negócios app do painel.
2. No painel de navegação esquerdo, escolha **usuários**.
3. Use o comando **Localizar** para localizar o (s) que você deseja mover para Skype para negócios Online.
4. Selecione o (s) e, no menu suspenso de **ação** acima da lista, selecione **mover usuários selecionados para Skype para negócios Online**.
5. No assistente, clique em **Avançar**.
6. Se solicitado, faça logon no Office 365, com uma conta que termina em. onmicrosoft.com e tem permissões suficientes.
7. Clique em **Avançar**e, em seguida, **Avançar** mais uma vez para mover o usuário.
8. Observe que as mensagens de status sobre o sucesso ou falha são fornecidas na parte superior do aplicativo principal do painel de controle, não no assistente.

## <a name="see-also"></a>Consulte também

[Move-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/move-csuser)