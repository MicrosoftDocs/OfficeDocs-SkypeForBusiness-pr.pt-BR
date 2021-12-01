---
title: Conexão Microsoft Teams Essentials (AAD Identidade) para um sistema de email existente com calendário
author: adjoseph
ms.author: adjoseph
ms.reviewer: jimmyw
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: Saiba como conectar o Microsoft Teams Essentials (AAD Identidade) a um sistema de email existente com calendário como o Google Workspace
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6d113446971375ace51335a6654c8599f8d2c35b
ms.sourcegitcommit: be8b820caf4b5a1a91ad444ba93da1df20bf63ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/01/2021
ms.locfileid: "61257493"
---
# <a name="connect-microsoft-teams-essentials-aad-identity-to-an-existing-email-system-with-calendar"></a>Conexão Microsoft Teams Essentials (AAD Identidade) para um sistema de email existente com calendário

Este guia fornece etapas de configuração para conectar o Microsoft Teams Essentials (AAD Identity) a um sistema de email existente com calendário.

Microsoft Teams Essentials (AAD Identity) reúne o melhor Teams reuniões, chat, chamada e colaboração. O Teams Essentials (AAD Identity) pode se conectar ao seu sistema de email existente para fornecer uma experiência integrada, como ter todas as notificações do Teams em uma caixa de entrada de email existente, todos os eventos de calendário no Teams e a capacidade de entrar no Teams com seu endereço de email existente.

Depois de conectado, você pode ver respostas a reuniões agendadas e convites para colaborar em sua caixa de correio e Microsoft Teams. Você também pode exibir e interagir com reuniões de entrada do seu calendário usando Teams software de reunião de terceiros, como o Google Workspace.

## <a name="prerequisites"></a>Pré-requisitos

As etapas de configuração neste artigo envolvem o processo de encaminhamento automático de itens de Exchange Online. Por padrão, o encaminhamento automático é desabilitado pela política de saída anti-spam. Essa política deve ser habilitada para conectar o Teams Essentials a um sistema de caixa de correio e calendário existente.

Para habilitar o encaminhamento automático:

1. Vá para o portal Microsoft 365 Defender em<https://security.microsoft.com/>
2. No menu de navegação à esquerda, acesse **Email & políticas** de colaboração & regras Políticas de ameaça  >    >    >  **Anti-spam** na seção Políticas
3. Na página **Políticas anti-spam,** selecione Política de saída **anti-spam (Padrão)** na lista
4. No sobremenu de detalhes da política exibido, selecione Editar configurações de **proteção** para modificar a regra de autoforwarding.
5. Em **Regras de encaminhamento**, altere a condição de encaminhamento automático para Ativado – o encaminhamento está **habilitado** e salva suas alterações.

:::image type="content" source="media/essentials-antispam.png" alt-text="Imagem mostrando o sub-sub-texto da política de saída anti-spam do Microsoft Defender Portal com Ativado, o encaminhamento está habilitado em Regras de encaminhamento." :::

Para saber mais sobre como configurar políticas de spam de saída, visite Configurar filtragem de spam de saída [- Office 365 | Microsoft Docs](/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide&preserve-view=true).

## <a name="connect-teams-essentials-to-exchange-online-with-exchange-on-premises"></a>Conexão Teams Essentials para Exchange Online com Exchange local

Você pode aproveitar tudo o que o Teams Essentials (AAD) tem a oferecer usando uma abordagem híbrida para configurar a conexão entre o Microsoft Teams e o Exchange Online com Exchange local.

Para fazer com que o acesso ao calendário funcione para suas caixas de correio locais, siga as diretrizes fornecidas em[Configuring Teams calendar access for Exchange on-premises mailboxes - Microsoft Tech Community](https://techcommunity.microsoft.com/t5/exchange-team-blog/configuring-teams-calendar-access-for-exchange-on-premises/ba-p/1484009)

Para implantar Salas do Microsoft Teams em um ambiente híbrido com Exchange local, visite [Deploy Salas do Microsoft Teams with Exchange local - Microsoft Teams | Microsoft Docs](rooms/with-exchange-on-premises.md)

## <a name="connect-teams-essentials-to-third-party-email-systems-with-calendar"></a>Conexão Teams Essentials para sistemas de email de terceiros com calendário

Se você não planeja alternar a caixa de correio da sua organização para Microsoft 365, você pode conectar o Teams Essentials a um sistema de calendário e email de terceiros existente. Essa conexão permite que você receba Teams notificações em seu sistema de email existente enquanto visualiza os convites de reunião existentes e eventos de calendário em Microsoft Teams.

### <a name="connect-teams-essentials-to-third-party-email-using-vanity-domain-google-workspace-example"></a>Conexão Teams Essentials para email de terceiros usando o domínio do vanity (exemplo do Google Workspace)

A seção a seguir mostra como se conectar Microsoft Teams a um sistema de email existente com o calendário, como o Google Workspace. Você realizará essa conexão deixando o sistema de email atual intacto, encaminhando todos os emails para Exchange Online, filtrando tudo, exceto emails do tipo de calendário. Ao fazer isso, os emails de calendário aparecem automaticamente no calendário Teams aceitos como emails de tipo provisórios e não-calendários são excluídos.

Todos os emails gerados Microsoft 365 são encaminhados para o Google Workspace para que os usuários recebam Teams lembretes e notificações. As identidades do usuário, como o email principal do usuário, podem ser duplicadas. O login único também é possível, mas não é necessário. Os usuários devem poder participar Teams reuniões do calendário de terceiros ou Teams calendário. Outro Teams recursos funcionarão conforme o esperado.

:::image type="content" source="media/essentials-googleworkspace.png" alt-text="Imagem que representa um diagrama do fluxo de emails entre o EXO e o Gmail":::

Esses exemplos dependem do [commandlet Conexão-ExchangeOnline](/powershell/module/exchange/connect-exchangeonline?view=exchange-ps&preserve-view=true) PowerShell que faz parte [do módulo Exchange Online PowerShell V2](/powershell/exchange/exchange-online-powershell-v2&preserve-view=true). Se você receber um erro ao executar o Conexão-ExchangeOnline, verifique se você seguiu as instruções recomendadas para instalar o módulo usando Instalar o módulo [EXO V2](/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps&preserve-view=true). Quando Connect-ExchangeOnline solicita credenciais, certifique-se de usar uma conta de administrador de locatários.

**Etapa Um: Configurar um novo domínio Microsoft 365 locatário**

1. Vá para o centro de administração em <https://admin.microsoft.com> .

2. Vá para **Configurar**  >  **Domínios e** selecione **Adicionar domínio** para adicionar seu domínio existente. Se você não adicionar um domínio, as pessoas em sua organização usarão o domínio onmicrosoft.com para seus endereços de email até que você o faça. Certifique-se de adicionar seu domínio antes de adicionar usuários, para que você não tenha que defini-los duas vezes.

3. Verifique o domínio com um registro TXT seguindo as etapas em [Verificar com um Registro TXT](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider?view=o365-worldwide&preserve-view=true).

4. Quando solicitado, selecione **Não permitir Microsoft 365 configurar DNS**.

5. Quando solicitado, deixe os registros MX existentes no local sem alterá-los.

6. Atualize o registro TXT SPF existente para incluir Microsoft 365.

7. Configure DomainKeys Identified Mail (DKIM) para Microsoft 365 seguindo estas etapas para configurar manualmente [o DKIM](/microsoft-365/security/office-365-security/use-dkim-to-validate-outbound-email?view=o365-worldwide&preserve-view=true).

8. Entre novamente no Centro de administração do Microsoft 365 para <https://admin.microsoft.com/AdminPortal/> habilitar o DKIM

9. No painel de navegação à esquerda, selecione  >  **Domínios de Instalação**

10. Usando a caixa de seleção, selecione o domínio existente não Microsoft (ex: JohannaL@contosolandscapting2.m365master.com) nas listas atuais de domínios.

11. Selecione o botão com **três pontos verticais** para abrir um menu.

12. No menu, selecione **Definir como padrão**

13. **Confirme o conjunto como** padrão na janela que parece definir seu domínio existente como padrão.
    :::image type="content" source="media/essentials-internalrelay2.png" alt-text="Imagem da caixa de diálogo de confirmação para definir o domínio como padrão":::

    Para obter mais orientações sobre como adicionar um domínio Microsoft 365, siga as etapas descritas em [Add a domain to Microsoft 365](https://support.office.com/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611?ui=en-US&rs=en-US&ad=US).

**Etapa Dois: adicionar usuários e atribuir Teams licenças do Essentials**

1. Vá para o centro de administração em <https://admin.microsoft.com> para adicionar um usuário individual

2. Vá para **Usuários**  >  **Usuários ativos** e selecione **Adicionar um usuário**

3. No painel **Configurar as noções básicas,** preencha as informações básicas do usuário e selecione **Next**.
    - **Nome:** Preencha o nome e sobrenome, nome de exibição e nome de usuário.
    - **Domínio:** Escolha o domínio para a conta do usuário. Por exemplo, se o nome de usuário do usuário for Jakob e o domínio for contoso.com, ele entrará usando jakob@contoso.com.
    - **Configurações de senha:** Escolha usar a senha de geração automática ou criar sua própria senha forte para o usuário.  Determine se você deseja enviar a senha em um email quando o usuário for adicionado.

4. No painel **Atribuir licenças de** produto, selecione o local e a licença apropriada para o usuário. Se você não tiver nenhuma licença disponível, ainda poderá adicionar um usuário e comprar mais licenças. Selecione Próximo.

5. No painel **Configurações opcionais,** expanda **Funções** se quiser tornar esse usuário um administrador. Expanda **informações de** perfil para adicionar informações adicionais sobre o usuário.

6. Selecione **Próximo**, revise as configurações do novo usuário, faça outras alterações, se necessário, em seguida, selecione **Concluir** a adição e feche.

Para adicionar vários usuários ao mesmo tempo, siga as etapas de recomendação em Adicionar usuários e atribuir licenças - Microsoft 365 [administrador | Microsoft Docs](/microsoft-365/admin/add-users/add-users?view=o365-worldwide&preserve-view=true)

**Etapa três: Configurar o Espaço de Trabalho do Google**

***Configure a entrega dupla de email para Microsoft 365 anexos de faixa e de faixa:***

1. Siga as etapas do Google para configurar a entrega dupla: <https://support.google.com/a/answer/9228551?hl=en>

2. Adicionar rota para Office 365

    - Vá para o console do Administrador do Google em <https://admin.google.com> )
    - Acesse Apps > Google Workspace > Gmail > Hosts.
    - Insira um nome de rota. (Por exemplo, Microsoft 365)
    - Escolha 'Host único' e insira o registro MX especificado para domínio em Microsoft 365 (Por exemplo: ContosoLandscaping2-m365master-com.mail.protection.outlook.com)

    **Método host inteligente para resolver o código de resposta ATTR35 quando o email é enviado para Exchange local/Exchange Online :**
    - Escolha 'Host único' e insira o registro MX para o domínio inicial do locatário como o host inteligente. O domínio inicial está no formato GUID.onmicrosoft.com. Um GUID é um valor exclusivo fornecido a todas as organizações como parte de seu registro no serviço. Um GUID é um inteiro de 128 bits (16 bytes) que pode ser usado em todos os computadores e redes sempre que um identificador exclusivo for necessário.
    - Você pode usar a linha de comando: nslookup -type MX GUID.onmicrosoft.com para resolver o registro MX (Por exemplo: contosolandscaping2.mail.protection.outlook.com)
    - Escolha **Porta:25**
    - Prossiga com as opções recomendadas

3. Configurar rota para Office 365

    - Abra o **console do Administrador do Google** em <https://admin.google.com>

    - Ir para **Aplicativos**  >  **Google Workspace**  >  **Gmail**  >  **Routing**

    - Na guia **Roteamento,** selecione **Configurar**

    - Insira **Nome** da regra. (Por exemplo, Gmail para Office 365)

    - Para **que as mensagens de email afetem**, selecione Recebimento interno e **de**  **entrada**

    - Em **Para os tipos de mensagens acima,** selecione Modificar **mensagem**

    - Em **Também entregar para**, selecione Adicionar mais **destinatários** e selecione **Adicionar para adicionar a rota de email secundária.**

    - Em **Destinatários,** selecione a seta para baixo "" e selecione **Avançado.**

    - Selecione **Alterar rota.**

    - Na lista, selecione a rota de email secundária que você criou anteriormente

    - Em **Anexos**, selecione **Remover anexos da mensagem**

    - Role para baixo e selecione **Salvar**.

***Adicione seu subdomínio no espaço de trabalho do Google para receber emails de Microsoft 365.***

  Em seguida, você criará regras de encaminhamento em Microsoft 365 caixas de correio para seu subdomínio. Escolha um subdomínio a ser usado no Google Workspace para receber emails de Microsoft 365 (por exemplo, g.contosolandscaping2.m365master.com)

1. Iniciar no **console administrador do Google** (em admin.google.com)

2. Vá para  >  **Domínios de Conta** Gerenciar  >  **Domínios**

3. Selecione **Adicionar um domínio**

4. Insira o nome de domínio selecionado

5. Selecionar **domínio de alias do usuário**

6. Selecione **Adicionar domínio & verificação inicial**

7. Aguarde até que a verificação seja concluída e atualize a página

8. Selecione **Ativar o Gmail**

9. Escolha **Ignorar a instalação do registro MX** e selecione **NEXT**

10. Na caixa **de diálogo Rotear emails** para outro servidor, anote o servidor para rotear emails para (por exemplo, aspmx.l.google.com) e selecione Uso de outro servidor de **email**

***Permitir que o email Microsoft 365 ignorar o filtro DE SPAM***

1. Encontre um header apropriado do locatário Microsoft 365 enviando um email para um usuário no espaço de trabalho do Google.

2. Abra a mensagem e selecione **Mostrar Original**

3. Escolha um header de email que identifique exclusivamente emails provenientes do seu Microsoft 365 locatário. (Por exemplo, X-MS-Exchange-CrossTenant-id: 92f60fc7-eab3-403b-9d7d-9d683bf0a4b5)

4. Vá para **o console do Administrador do Google** em <https://admin.google.com>

5. Ir para **Aplicativos**  >  **Google Workspace**  >  **Conformidade do Gmail**  >  

6. Navegue até **Conformidade de Conteúdo** e selecione **Configurar**

7. Dê um nome à configuração. Por exemplo, Allowlist Microsoft 365 email.

8. Em **mensagens de email para afetar a** verificação de entrada

9. Em **Adicionar expressões que descrevem o conteúdo que** você deseja pesquisar em cada mensagem, selecione se QUALQUER um dos seguintes corresponder à **mensagem**

10. Em **Expressões,** selecione **Adicionar** xi. Em **Adicionar configuração**, escolha **Advanced content match**

11. Em **Local** escolha **Headers Completos**

12. Em **Tipo de Combinação** escolha Texto **Completo**

13. Em conteúdo, insira o header de email que identifica exclusivamente o email proveniente do locatário do Microsoft 365 (Por exemplo, X-MS-Exchange-CrossTenant-id: 92f60fc7-eab3-403b-9d7d-9d683bf0a4b5)

14. Selecionar **Salvar**

15. Na caixa **Se as expressões acima corresponderem,** faça o campo a seguir > **Modificar** Mensagem e verifique Ignorar filtro de **spam** para esta mensagem em **Spam**.

16. Selecionar **Salvar**

**Etapa quatro: configurar Microsoft 365 configurações para a integração**

*Configurar conector para rotear emails de Microsoft 365 para o Gmail:*

1. Vá para o **Centro de Administração da Microsoft** em <https://admin.microsoft.com/AdminPortal>

2. Selecione **Mostrar tudo** no menu de navegação à esquerda.

3. Em **Centros de administração,** selecione **Exchange** para abrir o Exchange de administração em uma nova guia

4. No menu **Exchange** de navegação à esquerda do centro de administração, selecione Conectores de fluxo de emails , abra o menu de estouro  >  (...) e selecione Adicionar um conector

5. Em **Conexão na** nova janela do conector, selecione **Office 365**

6. Em **Conexão para** selecionar o servidor de email da sua organização, selecione **Próximo**

7. Insira um **Nome** para o novo conector (Ex: Para Gmail) e continue **Next**

8. Na seção **Uso do Conector,** selecione **Somente quando** eu tiver uma regra de transporte configurada que redireciona mensagens para esse conector e selecione **Next**.

9. Na seção Roteamento, insira o host de email inteligente apropriado (por exemplo, aspmx.l.google.com), selecione **+** e continue **Next**.

10. Na seção **Restrições de** segurança, aceite as configurações padrão selecionando **Next**

11. Na seção **Email de** validação, insira um endereço de email válido para o sistema do Gmail (por exemplo, johannal@g.contosolandscaping2.m365master.com), selecione o sinal de a mais **(+)** e selecione **Validar**

12. Aguarde a conclusão da validação e, se tiver êxito, pressione Next

13. Em **Conector de revisão,** verifique se a configuração está correta e pressione Criar Conector

14. Quando você vir a notificação criada pelo Conector, pressione **Done**

*Encaminhar emails de Microsoft 365 caixas de correio para o Gmail*

1. Use a **central Administração Microsoft 365 para** atualizar cada caixa de correio ou você pode usar um script do **PowerShell,** como o seguinte:

    ```powershell
    $forwardingDomain = "g.contosolandscaping2.m365master.com"
    Connect-ExchangeOnline
    $Mailboxes = Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"}
    Foreach ($mbx in $mailboxes) {
    
    Set-Mailbox $mbx.Identity -DeliverToMailboxAndForward $true -ForwardingSMTPAddress $($mbx.Alias,$forwardingDomain -join "@")
    } 
    ```

*Configurar Exchange Online para a regra de transporte de calendário*

1. A configuração dessa configuração aceitará automaticamente convites de calendário para que eles se mostrem no calendário Teams sem exigir que os usuários interajam com o convite no Outlook Web App.

2. O seguinte script pode ser usado para criar as regras de transporte:

    ```powershell
    Connect-ExchangeOnline
    New-TransportRule -Name "Direct to Calendar" -MessageTypeMatches Calendaring -SetHeaderName "X-MS-Exchange-Organization-CalendarBooking-Response" -SetHeaderValue Tentative
    New-TransportRule -Name "Direct to Calendar triage action" -MessageTypeMatches Calendaring -SetHeaderName "X-MS-Exchange-Organization-CalendarBooking-TriageAction" -SetHeaderValue MoveToDeletedItems
    
    ```

*Desabilitar Outlook na Web caixas de correio*

1. Siga as instruções em [Disable Outlook na Web for a mailbox in Exchange Online](/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-outlook-web-app&preserve-view=true) to disable Outlook na Web for mailboxes.

2. Você pode desabilitar Outlook na Web usando o **Centro de Administração Exchange ou** o **PowerShell**. Você pode usar o exemplo a seguir do PowerShell para desabilitar Outlook na Web todas as caixas de correio:

    ```powershell
    Connect-ExchangeOnline
    $Mailboxes = Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"}
    Foreach ($mbx in $mailboxes) {
    Set-CASMailbox $mbx.Identity -OWAEnabled $false
    }
    ```

**Etapa cinco: configurar Exchange Online domínio para retransmissão interna**

Esta etapa garante que o email seja enviado para o sistema de terceiros para resolução final.

1. Vá para o **Centro de Administração da Microsoft** em <https://admin.microsoft.com/AdminPortal>

2. Na navegação à esquerda, selecione **Mostrar tudo**

3. Em **Centros de Administração,** selecione **Exchange** para abrir Exchange centro de administração em uma nova guia

4. No **Exchange de administração,** selecione **Fluxo de** emails no menu de navegação à esquerda e selecione **Domínios aceitos**

5. Toque no nome de domínio configurado no sistema de terceiros (por exemplo, contosoLandscaping2.m365master.com)

    :::image type="content" source="media/essentials-internalrelay1.png" alt-text="Imagem mostrando as configurações Exchange centro de administração para fluxo de email.":::

6. Selecione **Retransmissão Interna** e clique em **Salvar**

    :::image type="content" source="media/essentials-internalrelay2.png" alt-text="Imagem mostrando o ato de salvar a configuração de retransmissão interna.":::

**Etapa Seis: Criar uma regra para excluir todos os emails de entrada para Exchange Online exceto calendário**

1. Você pode configurar essa regra no Centro de administração **Exchange** ou **no PowerShell**. Você pode usar o seguinte **exemplo do PowerShell** para criar a regra:

    ```powershell
    Connect-ExchangeOnline
    New-TransportRule -Name "Delete all except Calendaring" -ExceptIfMessageTypeMatches Calendaring -FromScope NotInOrganization -DeleteMessage:$true 
    
    ```

### <a name="connect-teams-essentials-to-third-party-email-not-using-vanity-domain-gmail-example"></a>Conexão Teams Essentials para email de terceiros que não usam domínios de vaidade (exemplo do Gmail)

Você pode agendar e ingressar em uma reunião de Teams diretamente do Google Workspace conectando uma conta do Gmail de consumidor ao Teams Essentials com base principal no [Teams G Suite Add On](https://support.microsoft.com/en-us/office/install-the-teams-meeting-add-on-for-google-workspace-bba2dfbe-0b2b-4ee7-be10-261ad80ddb60). Isso oferece a oportunidade de agendar vídeo e audioconferência com compartilhamento de tela, chat de reunião, quadro de comunicação digital e muito mais.

Você configurará o Gmail para receber emails do Exchange Online para garantir que os emails gerados no Microsoft 365 e Teams cheguem com êxito no Gmail. Os padrões de segurança podem precisar ser desabilitados para realizar essa conexão, o que torna essencial o uso de uma senha forte e exclusiva. Um domínio personalizado não é necessário para esse cenário, mas ele pode ser configurado no Microsoft 365 para uso no Gmail se você quiser usar um.

:::image type="content" source="media/essentials-gmail.png" alt-text="Imagem que depisa o fluxo de emails entre o Teams Essentials e o Gmail":::

**Verifique se você tem uma conta do Gmail configurada.**

Se você já tiver uma conta existente, poderá prosseguir para a próxima etapa. Caso não seja, visite [Criar nova conta do Google](https://accounts.google.com/SignUp?hl=en) para configurar uma nova conta do Gmail.

**2. Configurar seu locatário Microsoft 365 locatário**

*Configurar Teams AAD usuários*

1. Siga as diretrizes em[Adicionar usuários e atribuir licenças](/microsoft-365/admin/add-users/add-users?view=o365-worldwide&preserve-view=true) para adicionar vários usuários

*Configurar a proteção de identidade*

1. Desabilitar os padrões de segurança se estiver ativo.

2. Configurar autenticação multifator para usuários

3. Se estiver usando o acesso condicional, certifique-se de abrir exceção para o acesso POP à caixa de correio

*Adicionar domínio ao Administração Microsoft 365 Central (opcional)*

1. Em navegação, selecione Configurações > Domínio e selecione Adicionar domínio

2. Insira seu nome de domínio no campo apropriado

3. Siga as instruções na tela para verificar seu domínio com registro TXT

4. Quando solicitado, permita que a Microsoft configure o DNS

5. Conclua as instruções para verificar a rota do registro MX para Microsoft 365

6. Configurar o registro TXT do SPF para incluir Microsoft 365

7. Conclua as instruções para configurar registros TXT DKIM para Microsoft 365

8. Verifique se o DKIM está habilitado fazendo logo out e entrando novamente no Centro de administração

**3. Configurar o Gmail**

1. Configurar o Gmail para Exchange Online email em seu sistema

2. Configurar o Teams de calendário

3. Habilitar o Gmail para usar o domínio comercial (opcional)
