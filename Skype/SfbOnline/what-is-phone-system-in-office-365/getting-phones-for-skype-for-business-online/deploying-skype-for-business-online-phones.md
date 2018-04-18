---
title: Implantar telefones para o Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.assetid: faa17eb3-7483-4984-87f2-815d981b68ae
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
- Strat_SB_PSTN
description: Conheça as etapas de implantação para obter o firmware correto, atualizá-la, se necessário, atribuir licenças e definir configurações para Skype para telefones online de negócios
ms.openlocfilehash: 2e1ee62dc2cd16a8aeec9b1eb744e4ca3f0155eb
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/18/2018
---
# <a name="deploying-skype-for-business-online-phones"></a>Implantar telefones para o Skype for Business Online

Este guia de implantação ajudará você a implantar os telefones IP do Skype for Business Online.
  
Em todos os tipos de empresas, ter um número de telefone permite aos usuários fazer e receber chamadas de voz e é um requisito importante para fazer negócios. Os usuários que possuem números de telefone poderão fazer chamadas de voz entre todos os Skype para dispositivos de negócios, incluindo telefones IP, PCs e dispositivos móveis. Você pode aprender mais sobre Skype para telefones IP Business lendo [telefones de Introdução para Skype para negócios Online](getting-phones-for-skype-for-business-online.md).
  
## <a name="deployment-steps-for-ip-phones"></a>Etapas da implantação para telefones IP

### <a name="step-1---download-the-manufacturers-administrator-guides-and-phone-manuals"></a>Etapa 1 - Baixe os guias de administrador do fabricante e manuais do telefone

Antes de iniciar, é recomendável baixar os guias de administração do fabricante e dos manuais do usuário do telefone.
  
- Para telefones Polycom, consulte o [Polycom Deployment Guide] ((http://www.polycom.com/voice-conferencing-solutions/desktop-ip-phones.html).
    
- Para telefones Yealink, consulte [Yealink Skype para a solução de telefones SIP do negócios HD](http://www.yealink.com/products_top_2.html).
    
- Para telefones AudioCodes, consulte o [Guia de Gerenciamento de Provisionamento Audiocodes ](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions).
    
### <a name="step-2---make-sure-youre-purchasing-or-migrating-a-skype-for-business-supported-ip-phone-and-firmware"></a>Etapa 2 - Certifique-se de que você está migrando para um telefone IP e firmware compatíveis com o Skype for Business ou adquirindo um assim.

Um telefone e um firmware compatíveis com o Skype for Business Online também são compatíveis com o Skype for Business Server, mas o oposto nem sempre é aplicável. Para certificar-se você estiver comprar ou um telefone com suporte e firmware de provisionamento, consulte [Getting telefones para Skype para negócios Online](getting-phones-for-skype-for-business-online.md).
  
### <a name="step-3---checking-that-the-right-firmware-is-installed-and-update-the-firmware-if-required"></a>Etapa 3 - Verificar se o firmware certo foi instalado e atualizar o firmware, se necessário

Verifica a versão de firmware em seus telefones. No caso de:
  
- **Telefones Polycom VVX**, vá para **Configurações** > **Status** > **Plataforma** > **Aplicativo** > **Principal**.
    
- **Telefones Yealink**, vá para **Status** na tela do telefone principal.
    
- **AudioCodes phones**, go to **Menu** > **Device Status** > **Firmware version** from the start screen.
    
    > [!NOTE]
    > Para obter acesso remoto para obter detalhes de telefone, consulte guias de administração do fabricante. Consulte os links acima para os guias de usuário e manuais de telefone. 
  
- **Telefones Lync Phone Edition (LPE)**, vá para **Menu** > **Informações do Sistema** na tela inicial.
    
### <a name="step-4---device-update-considerations"></a>Etapa 4 - Considerações sobre atualização do dispositivo

> [!NOTE]
> Polycom firmware antes da 5.5.1.X tinha um mecanismo de bloqueio de dispositivo específicas do fabricante é substituído por um Skype para a implementação de negócios "Telefone-Lock." Atualizando um telefone do 5.4.X.X que tenha sido protegido com "Bloqueio de dispositivo" para 5.5.1.X com "Bloqueio de telefone" não herda o código PIN de "Dispositivo-Lock," que pode deixar o telefone não segura. Os usuários que ativaram "Bloqueio de dispositivo" precisam habilitar o seguinte parâmetro de perfil do dispositivo Polycom dar aos usuários controle de tempo de atualização (lync.deviceUpdate.popUpSK.enabled=1). 
  
As atualizações de firmware são gerenciadas pelo Serviço do Skype for Business. Todo firmware de telefone certificado pelo Skype for Business é carregado para o servidor de atualização do Skype for Business e a atualização do dispositivo é habilitada em todos os telefones por padrão. Dependendo do tempo de inatividade no telefone e nos intervalos de sondagem, os telefones baixarão e instalarão automaticamente os builds certificados mais recentes. Você pode desabilitar as configurações de atualização de dispositivo usando o cmdlet [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) e definindo o parâmetro _EnableDeviceUpdate_ para `false`.
  
![Deploying phones.](../../images/be727622-1924-439f-96ca-89230739db9e.png)
  
Quando um novo firmware está disponível e pronto para baixar e instalar, o telefone notificará o usuário. Telefones Polycom irá notificar o usuário e fornecer-lhes uma opção para **atualização** ou **Adiar**.
  
![Deploying phones.](../../images/50956fa0-da0c-4085-9bb5-4a2e99aecebb.png)
  
Para um telefone Polycom, você pode atualizar o firmware no telefone selecionando **SwUpdate**.
  
![Deploying phones.](../../images/376c1998-6ce6-44b6-a84d-ae7d96b1c307.png)
  
Você também pode optar por gerenciar as atualizações de firmware usando um sistema de provisionamento de parceiros. Para o gerenciamento do sistema de provisionamento de parceiros incluindo a personalização avançada do telefone, consulte os guias de administração do fabricante.
  
> [!CAUTION]
> [!CUIDADO] Certifique-se de ter uma única autoridade de atualização de dispositivo (atualização de dispositivo em banda ou um servidor de provisionamento de terceiro) para evitar loops de atualização. 
  
### <a name="step-5---configuration-and-infrastructure-phone-settings"></a>Etapa 5 - configuração e definições de telefone de infra-estrutura

Você pode configurar as opções e as políticas do telefone usadas com mais frequência usando os cmdlets do Windows PowerShell de gerenciamento em banda do Skype for Business. Consulte [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) para obter detalhes sobre esses parâmetros e configurações.
  
Para o planejamento da infra-estrutura de rede, consulte [Skype Operations Framework](https://www.skypeoperationsframework.com/).
  
### <a name="step-6---preparing-for-users-to-sign-in"></a>Etapa 6 - Preparando os usuários entrem em

Para habilitar usuários entrar em um Skype para telefone comercial Online e fazer chamadas com êxito, você precisará certificar-se de que os usuários recebem as licenças corretas. No mínimo, você precisará atribuir uma licença de sistema telefônico e um plano de chamada. Para obter informações adicionais, você pode ver [Skype para licenciamento de complemento de negócios e equipes da Microsoft](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) e [Atribuir Skype para licenças de negócios e equipes da Microsoft](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).
  
Você pode encontrar mais informações sobre planos de chamar lendo [Cite chamar planos no Office 365?](../../what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365.md)
  
- As **opções de logon** que estão disponíveis para os usuários online são:
    
  - Usuários com telefones **Polycom VVX 5XX/6XX** verá:
    
     ![Deploying phones.](../../images/8a1ffb33-8a63-4242-bb76-d5fafb6a6472.png)
  
  - Usuários com telefones **Yealink T48G/T46G** verá:
    
     ![Yealink phones logon.](../../images/2a2892ae-850d-4781-8be0-4ffb8af068c9.png)
  
    Para obter detalhes sobre as opções de entrar suportadas pelo fabricante, consulte [Getting telefones para Skype para negócios Online](getting-phones-for-skype-for-business-online.md).
    
- **ID do usuário** Usando o teclado do telefone ou o teclado na tela (se disponível), os usuários podem usar o nome e a senha do usuário de sua organização para fazer logon no telefone. Por exemplo, os usuários devem usar o formato UPN como *amosm@contoso.com*  para seu nome de usuário.
    
     ![Deploying phones.](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
    > [!NOTE]
    > [!OBSERVAçãO] A autenticação de PIN não é aceita no Skype for Business Online para telefones LPE e telefones IP de parceiros. 
  
- **Usando um PC** Quando a união de forças sobre software Ethernet (BToE) está instalado no PC do usuário e habilitado, os usuários podem fazer logon no seus telefones usando a janela de autenticação em seus Skype do Windows para o aplicativo de negócios. Consulte a [etapa 7 (opcional) - se você tiver o emparelhamento de dispositivos e Better Together over Ethernet (BToE)](deploying-skype-for-business-online-phones.md#BK_BTOE) para obter outras informações.
    
    > [!NOTE]
    > [!OBSERVAçãO] Os usuários devem usar o nome de usuário e senha da organização para fazer logon no telefone. Por exemplo, os usuários devem usar o formato UPN como  *amosm@contoso.com*  para seu nome de usuário.
  
     ![Deploying phones.](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
- **Usando um Web entrar**: essa é uma maneira de nova para usuários on-line autenticar usando um navegador da web padrão. Os usuários serão fornecidos com um conjunto de instruções a seguir quando utilizarem um navegador para entrar.
    
  - Usuários com telefones **Polycom VVX 5XX/6XX** verá:
    
     ![Deploying phones.](../../images/ba0df923-a6e5-4a9b-b40b-b03ca188e814.png)
  
  - Usuários com telefones **Yealink T48G/T46G** verá:
    
     ![Yealink phone logon.](../../images/86551cc3-533a-4694-9683-bad907c9ad5a.png)
  
    O código que seja gerado expirará em 15 minutos. Quando ela expira, o usuário precisará clique em **Repetir** ou **Okey** para gerar um novo código, dependendo do telefone.
    
  - Usuários com telefones **Polycom VVX 5XX/6XX** verá:
    
     ![PIN code expired.](../../images/b5d27037-aa26-4054-be95-d5a6c293d08c.png)
  
  - Usuários com telefones **Yealink T48G/T46G** verá:
    
     ![Yealink phones logon.](../../images/3a4462ac-0c59-409e-a3bb-1451cdcc8676.png)
  
    Usando um navegador, navegue até o endereço exibido no telefone e digite o nome do usuário do Skype for Business.
    
     ![Deploying phones.](../../images/7c540b85-dc37-4ce7-a077-9e3454a0efd0.png)
  
    Digite o código mostrado no telefone.
    
     ![Deploying phones.](../../images/d6b88016-35d2-41d1-a0da-81fef34521d4.png)
  
    Verifique se o site mostra "[nome do fabricante do telefone] **Skype para negócios Certified Phone**," e clique em **continuar**.
    
     ![Deploying phones.](../../images/a8252b37-4ff5-4ece-9e2a-3e05bf928299.png)
  
    Clique nas credenciais do usuário ou clique em **Usar outra conta**:
    
     ![Deploying phones.](../../images/8415028b-7924-4747-b639-052d9b0b961e.png)
  
    Quando for exibida a página seguinte, é seguro fechar o navegador.
    
     ![Deploying phones.](../../images/1a873201-52fc-4a63-b7b5-e82bbd031fd2.png)
  
    > [!NOTE]
    > [!OBSERVAçãO] Os telefones LPE para Skype for Business Online permitem logon somente por meio de compartilhamento USB. 
  
- **Implantações suportadas** A tabela abaixo mostra os tipos de autenticação permitidos para os modelos de implantação aceitos atualmente incluindo a Integração com o Exchange, Autenticação moderna com o MFA (Multi-factor Authentication, Autenticação Multifator) e o Skype for Business Online e locais.
    
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Skype for Business** <br/> |**Exchange** <br/> |**Método de entrada de telefone** <br/> |**Skype para acesso de negócios** <br/> |**Acesso do Exchange com Autenticação Multifator e MFA desabilitados** <br/> |**Acesso do Exchange com Autenticação Multifator e MFA habilitados** <br/> |
|Online  <br/> |Online  <br/> |Entrada da Web  <br/> |Sim  <br/> |Sim  <br/> |Sim  <br/> |
|Online  <br/> |Online  <br/> |Nome do usuário/Senha  <br/> |Sim  <br/> |Sim  <br/> |Não  <br/> |
|Online  <br/> |Locais  <br/> |Entrada da Web  <br/> |Sim  <br/> |Não  <br/> |Não  <br/> |
|Online  <br/> |Locais  <br/> |Nome do usuário/Senha  <br/> |Sim  <br/> |Sim  <br/> |Não  <br/> |
|Locais  <br/> |Online/Locais  <br/> |Autenticação de PIN  <br/> |Sim  <br/> |Não  <br/> |Não  <br/> |
|Locais  <br/> |Online/Locais  <br/> |Nome do usuário/Senha  <br/> |Sim  <br/> |Sim  <br/> |N/A  <br/> |
|Locais  <br/> |Online/Locais  <br/> |Entrada via PC (BTOE)  <br/> |Sim  <br/> |Sim  <br/> |N/A  <br/> |
   
- **Recursos de telefone** O conjunto de recursos pode variar ligeiramente com base no parceiro do telefone IP. Para o recurso completo definida e para saber mais sobre os recursos para cada fabricante do telefone, consulte [Getting telefones para Skype para negócios Online](getting-phones-for-skype-for-business-online.md).
    
- **Bloqueio de telefone** é um recurso introduzido recentemente nos telefones certificados pelo Skype for Business que é usado para proteger um telefone. Se habilitada, os usuários serão solicitados para criar um PIN após a autenticação bem-sucedida. Depois de criado, os telefones serão bloqueados quando o tempo ocioso-limite que você definir expirar, um usuário bloqueia manualmente seu telefone ou ele sincroniza o bloqueio do telefone com o bloqueio do PC usando o Emparelhamento de Telefone. Se o PIN de bloqueio de telefone for inserido errado várias vezes, o telefone irá desconectar o usuário ou requerem código do administrador para desbloquear o telefone, mas isso irá variar dependendo do parceiro de telefone. O PIN do usuário deve estar entre 6 e 15 dígitos.
    
    Você pode desabilitar o bloqueio de telefone para sua organização (que é habilitada por padrão), alterar o limite de ociosidade e escolher se os usuários podem fazer chamadas telefônicas enquanto eles estão bloqueadas ou não usando configurações de inband. Consulte [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) para obter mais detalhes sobre essas configurações.
    
## <a name="step-7-optional---if-you-have-device-pairing-and-better-together-over-ethernet-btoe"></a>Etapa 7 (opcional) - Se você tiver emparelhamento de dispositivo e Better Together over Ethernet (BToE)
<a name="BK_BTOE"> </a>

BToE é um telefone paining mecanismo para telefones IP de parceiro que pares de telefone de um usuário com seus Skype do Windows para o aplicativo de negócios. BToE habilita os usuários a:
  
- Entrar no seu telefone IP usando seu Skype para aplicativos da área de trabalho de negócios (usando um PC)
    
- Sincronizar o bloqueio de telefone com o bloqueio de PC
    
- Clique para chamar
    
BToE pode ser configurado para operar em dois modos: *Manual* e *automático* (padrão). Ele também pode ser habilitado (padrão)/desabilitado para usuário que usam as configurações em banda do Skype for Business. Ao operar no modo *Manual*  , os usuários terão que executar um passo adicional para emparelhar o telefone ao app Windows.
  
 **Implantar BToE para os usuários**
  
1. Conecte o PC deles ao telefone usando a porta do PC.
    
     ![Deploying phones.](../../images/e21d76c7-867c-4fe6-95c6-fc40c608ed0c.png)
  
2. Baixe e instale o software BToE mais recente do site do fabricante usando os links abaixo. Para uma melhor experiência do usuário, você pode distribuir e instalar o software BToE usando uma solução de distribuição de administração como o SCCM (System Center Configuration Manager). Para obter ajudar sobre como usar o SCCM, consulte [Pacotes e programas no System Center Configuration Manager](https://docs.microsoft.com/en-us/sccm/apps/deploy-use/packages-and-programs).
    
  - [Site de Download de Software do Polycom BToE](http://www.polycom.com/voice-conferencing-solutions/microsoft-phones.html)
    
  - [Download de software BToE Yealink](http://www.yealink.com/products_list_10.html)
    
  - [Downloads de software BToE AudioCodes](https://www.audiocodes.com/solutions-products/solutions/skype-for-business-microsoft-teams/skype-for-business-online)
    
3. Por padrão, a configuração de servidor para BToE é definida como **ativado** e o **modo automático** . Para alterar essas configurações, consulte [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx).
    
> [!NOTE]
> [!OBSERVAçãO] O BToE não é permitido atualmente nas plataformas Mac e VDI. 
  
## <a name="related-topics"></a>Tópicos relacionados
[Obtendo números de telefone de serviço do Skype for Business e do Microsoft Teams](../../what-is-phone-system-in-office-365/getting-service-phone-numbers.md)

Eis o que você obtém com o [Sistema de Telefonia no Office 365](../../what-is-phone-system-in-office-365/here-s-what-you-get-with-phone-system.md)

[Disponibilidade da Audioconferência e dos Planos de Chamadas por país e região](../../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

  
 
