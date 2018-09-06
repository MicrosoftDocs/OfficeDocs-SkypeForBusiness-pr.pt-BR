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
localization_priority: Priority
f1keywords: None
ms.custom:
- Phone System
description: Aprenda as etapas de implantação para obter o firmware correto, atualize-o se necessário, atribua licenças e defina configurações para os telefones do Skype for Business Online
ms.openlocfilehash: 4237e1cb32204a3d87d639710a2829c1111cc354
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2018
ms.locfileid: "23780058"
---
# <a name="deploying-skype-for-business-online-phones"></a>Implantar telefones do Skype for Business Online

Este guia de implantação ajudará você a implantar os telefones IP do Skype for Business Online.
  
Em todos os tipos de empresas, ter um número de telefone permite que os usuários façam e recebam chamadas de voz, o que é importante para fazer negócios. Os usuários com números de telefone podem fazer chamadas de voz em todos os dispositivos com o Skype for Business incluindo telefones IP, PCs e dispositivos móveis. Você pode saber mais sobre os telefones IP do Skype for Business consultando Obter telefones para o Skype for Business Online.[ ](getting-phones-for-skype-for-business-online.md)
  
## <a name="deployment-steps-for-ip-phones"></a>Etapas de implantação para telefones IP

### <a name="step-1---download-the-manufacturers-administrator-guides-and-phone-manuals"></a>Etapa 1 - Baixe os guias de administrador do fabricante e manuais do telefone

Antes de iniciar, é recomendável baixar os guias de administração do fabricante e dos manuais do usuário do telefone.
  
- Para telefones Polycom, consulte o [Guia de implantação Polycom]((http://www.polycom.com/voice-conferencing-solutions/desktop-ip-phones.html).
    
- Para telefones Yealink, consulte [Solução para telefones SIP HD Yealink para Skype for Business](http://www.yealink.com/products_top_2.html).
    
- Para telefones AudioCodes, consulte o [Guia de Gerenciamento de Provisionamento Audiocodes ](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions).
    
### <a name="step-2---make-sure-youre-purchasing-or-migrating-a-skype-for-business-supported-ip-phone-and-firmware"></a>Etapa 2 - Certifique-se de que você está adquirindo ou migrando um telefone IP e firmware compatíveis com o Skype for Business

Um telefone e um firmware compatíveis com o Skype for Business Online também são compatíveis com o Skype for Business Server, mas o oposto nem sempre é verdade. Para ter certeza de que está comprando ou provisionando um telefone e firmware compatíveis, consulte [Obter telefones para o Skype for Business Online](getting-phones-for-skype-for-business-online.md).
  
### <a name="step-3---checking-that-the-right-firmware-is-installed-and-update-the-firmware-if-required"></a>Etapa 3 - Verificar se o firmware certo foi instalado e atualizá-lo, se necessário

Verifique a versão do firmware do seu telefone. No caso de:
  
- **Telefones Polycom VVX**, vá para **Configurações** > **Status** > **Plataforma** > **Aplicativo** > **Principal**.
    
- **Telefones Yealink**, vá para **Status** na tela do telefone principal.
    
- **Telefones AudioCodes**, acesse **Menu** > **Status do Dispositivo** > **Versão do firmware** na tela inicial.
    
    > [!NOTE]
    > Para obter acesso remoto aos detalhes do telefone, consulte os guias de administração do fabricante. Veja os links acima para acessar os guias de usuário e os manuais de telefone. 
  
- **Telefones Lync Phone Edition (LPE)**, vá para **Menu** > **Informações do Sistema** na tela inicial.
    
### <a name="step-4---device-update-considerations"></a>Etapa 4 - Considerações sobre atualização do dispositivo

> [!NOTE]
> O firmware da Polycom anterior à versão 5.5.1.X tinha um mecanismo de bloqueio de dispositivo específico do fabricante que foi substituído pelo "Bloqueio de telefone" implementado no Skype for Business. A atualização de um telefone versão 5.4.X.X que era protegido pelo "Bloqueio de Dispositivo" para a versão 5.5.1.X com o "Bloqueio de Telefone" não herdará o código PIN do "Bloqueio de Dispositivo", o que pode deixar o telefone desprotegido. Para os usuários que têm o "Bloqueio de Dispositivo" ativado, é necessário habilitar o seguinte parâmetro do Perfil de Dispositivo Polycom para ter controle do momento da atualização (lync.deviceUpdate.popUpSK.enabled=1). 
  
As atualizações de firmware são gerenciadas pelo Serviço do Skype for Business. Todo firmware de telefone certificado pelo Skype for Business é carregado no servidor de atualização do Skype for Business e a atualização do dispositivo é habilitada em todos os telefones por padrão. Dependendo do tempo de inatividade do telefone e dos intervalos de sondagem, as versões certificadas atuais serão baixadas e instaladas automaticamente. Você pode desabilitar as configurações de atualização do dispositivo usando o cmdlet [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) e definindo o parâmetro _EnableDeviceUpdate_ como `false`.
  
![Implementar telefones.](../../images/be727622-1924-439f-96ca-89230739db9e.png)
  
Quando um novo firmware está disponível e pronto para download e instalação, o telefone notifica o usuário. Os telefones Polycom notificam o usuário e oferecem as opções **Atualizar** ou **Adiar**.
  
![Implementar telefones.](../../images/50956fa0-da0c-4085-9bb5-4a2e99aecebb.png)
  
Para um telefone Polycom, você pode atualizar o firmware no telefone selecionando **SwUpdate**.
  
![Implementar telefones.](../../images/376c1998-6ce6-44b6-a84d-ae7d96b1c307.png)
  
Você também pode optar por gerenciar as atualizações de firmware usando um sistema de provisionamento de parceiros. Para o gerenciamento do sistema de provisionamento de parceiros incluindo a personalização avançada do telefone, consulte os guias de administração do fabricante.
  
> [!CAUTION]
> [!CUIDADO] Certifique-se de ter uma única autoridade de atualização de dispositivo (atualização de dispositivo em banda ou um servidor de provisionamento de terceiro) para evitar loops de atualização. 
  
### <a name="step-5---configuration-and-infrastructure-phone-settings"></a>Etapa 5 - Configuração e infraestrutura do telefone

Você pode configurar as opções e as políticas do telefone usadas com mais frequência usando os cmdlets do Windows PowerShell de gerenciamento em banda do Skype for Business. Consulte [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) para obter detalhes sobre esses parâmetros e configurações.
  
Para o planejamento da infraestrutura de rede, consulte [Estrutura das operações do Skype](https://www.skypeoperationsframework.com/).
  
### <a name="step-6---preparing-for-users-to-sign-in"></a>Etapa 6 - Preparação para entrada dos usuários

Para habilitar os usuários a entrarem com sucesso em um telefone do Skype for Business Online e fazer chamadas, você precisa verificar se licenças corretas foram atribuídas. No mínimo, será necessário atribuir uma licença do Plano de Telefonia e um Plano de Chamadas. Para obter mais informações, consulte [Licenças Complementares do Skype for Business](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) e[Atribuir licenças do Skype for Business e Microsoft Teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).
  
Você pode encontrar mais informações sobre Planos de Chamadas em [O que são os Planos de Chamadas do Office 365?](/microsoftteams/what-are-calling-plans-in-office-365)
  
- As **opções de logon** que estão disponíveis para os usuários online são:
    
  - Os usuários com telefones **Polycom VVX 5XX/6XX** verão:
    
     ![Implementar telefones.](../../images/8a1ffb33-8a63-4242-bb76-d5fafb6a6472.png)
  
  - Os usuários com os telefones **Yealink T48G/T46G** verão:
    
     ![Logon de telefones Yealink.](../../images/2a2892ae-850d-4781-8be0-4ffb8af068c9.png)
  
    Para obter detalhes sobre as opções entrada aceitas pelo fabricante, consulte [Obter telefones para o Skype for Business Online](getting-phones-for-skype-for-business-online.md).
    
- **ID do usuário** Usando o teclado do telefone ou o teclado na tela (se disponível), os usuários podem usar o nome e a senha do usuário de sua organização para fazer logon no telefone. Por exemplo, os usuários devem usar o formato UPN como *amosm@contoso.com*  para seu nome de usuário.
    
     ![Implementar telefones.](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
    > [!NOTE]
    > [!OBSERVAçãO] A autenticação de PIN não é aceita no Skype for Business Online para telefones LPE e telefones IP de parceiros. 
  
- **Ao usar um PC** com o software Better Together over Ethernet (BToE) instalado e habilitado, os usuários podem fazer logon no telefone usando a janela de autenticação do aplicativo Skype for Business para Windows. Consulte[Etapa 7 (opcional) - Se você tem emparelhamento de dispositivo e Better Together over Ethernet (BToE)](deploying-skype-for-business-online-phones.md#BK_BTOE) para obter outras informações.
    
    > [!NOTE]
    > [!OBSERVAçãO] Os usuários devem usar o nome de usuário e senha da organização para fazer logon no telefone. Por exemplo, os usuários devem usar o formato UPN como  *amosm@contoso.com*  para seu nome de usuário.
  
     ![Implementar telefones.](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
- **Usar entrada via Web**: Essa é uma nova maneira de os usuários online autenticarem usando um navegador padrão. Eles receberão um conjunto de instruções para usar um navegador para entrar.
    
  - Os usuários com telefones **Polycom VVX 5XX/6XX** verão:
    
     ![Implementar telefones.](../../images/ba0df923-a6e5-4a9b-b40b-b03ca188e814.png)
  
  - Os usuários com os telefones **Yealink T48G/T46G** verão:
    
     ![Logon de telefone Yealink.](../../images/86551cc3-533a-4694-9683-bad907c9ad5a.png)
  
    O código gerado expira em 15 minutos. Após expirar, o usuário terá que clicar em **Tentar novamente** ou **OK** para gerar um novo código dependendo do telefone.
    
  - Os usuários com telefones **Polycom VVX 5XX/6XX** verão:
    
     ![Código PIN expirado.](../../images/b5d27037-aa26-4054-be95-d5a6c293d08c.png)
  
  - Os usuários com os telefones **Yealink T48G/T46G** verão:
    
     ![Logon de telefones Yealink.](../../images/3a4462ac-0c59-409e-a3bb-1451cdcc8676.png)
  
    Usando um navegador, navegue até o endereço exibido no telefone e digite o nome do usuário do Skype for Business.
    
     ![Implementar telefones.](../../images/7c540b85-dc37-4ce7-a077-9e3454a0efd0.png)
  
    Digite o código mostrado no telefone.
    
     ![Implementar telefones.](../../images/d6b88016-35d2-41d1-a0da-81fef34521d4.png)
  
    Verifique se o site mostra o "Telefone [nome do fabricante do telefone] **certificado pelo Skype for Business**", e clique em **Continuar**.
    
     ![Implementar telefones.](../../images/a8252b37-4ff5-4ece-9e2a-3e05bf928299.png)
  
    Clique nas credenciais do usuário ou clique em **Usar outra conta**:
    
     ![Implementar telefones.](../../images/8415028b-7924-4747-b639-052d9b0b961e.png)
  
    Quando a página seguinte for exibida, é seguro fechar o navegador.
    
     ![Implementar telefones.](../../images/1a873201-52fc-4a63-b7b5-e82bbd031fd2.png)
  
    > [!NOTE]
    > [!OBSERVAçãO] Os telefones LPE para Skype for Business Online permitem logon somente por meio de compartilhamento USB. 
  
- **Implantações suportadas** A tabela abaixo mostra os tipos de autenticação permitidos para os modelos de implantação aceitos atualmente incluindo a Integração com o Exchange, Autenticação moderna com o MFA (Multi-factor Authentication, Autenticação Multifator) e o Skype for Business Online e locais.
    
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Skype for Business** <br/> |**Exchange** <br/> |**Método de entrada de telefone** <br/> |**Acesso ao Skype For Business** <br/> |**Acesso do Exchange com Autenticação Multifator e MFA desabilitados** <br/> |**Acesso do Exchange com Autenticação Multifator e MFA habilitados** <br/> |
|Online  <br/> |Online  <br/> |Entrada da Web  <br/> |Sim  <br/> |Sim  <br/> |Sim  <br/> |
|Online  <br/> |Online  <br/> |Nome do usuário/Senha  <br/> |Sim  <br/> |Sim  <br/> |Não  <br/> |
|Online  <br/> |Locais  <br/> |Entrada da Web  <br/> |Sim  <br/> |Não  <br/> |Não  <br/> |
|Online  <br/> |Locais  <br/> |Nome do usuário/Senha  <br/> |Sim  <br/> |Sim  <br/> |Não  <br/> |
|Locais  <br/> |Online/Locais  <br/> |Autenticação por PIN  <br/> |Sim  <br/> |Não  <br/> |Não  <br/> |
|Locais  <br/> |Online/Locais  <br/> |Nome do usuário/Senha  <br/> |Sim  <br/> |Sim  <br/> |N/D  <br/> |
|Locais  <br/> |Online/Locais  <br/> |Entrada via PC (BTOE)  <br/> |Sim  <br/> |Sim  <br/> |N/D  <br/> |
   
- **Recursos de telefone** O conjunto de recursos pode variar ligeiramente com base no parceiro do telefone IP. Para o conjunto completo e para saber mais sobre os recursos de cada fabricante de telefone, consulte [Obter telefones do Skype for Business Online](getting-phones-for-skype-for-business-online.md).
    
- **Bloqueio de telefone** é um recurso introduzido recentemente nos telefones certificados pelo Skype for Business usado para proteção. Se habilitado, os usuários precisam criar um PIN após a autenticação bem-sucedida. Após criado, os telefones são bloqueados após o limite de tempo ocioso definido, manualmente pelo usuário, ao sincronizar o bloqueio do telefone com o bloqueio do PC usando o Emparelhamento de Telefone. Se o PIN de bloqueio de telefone incorreto for inserido várias vezes, o telefone desconectará o usuário ou exigirá um código de administrador para o desbloqueio, mas isso varia dependendo do parceiro de telefonia. O PIN do usuário deve ter entre 6 e 15 dígitos.
    
     Você pode desabilitar o bloqueio do telefone para a sua organização (é habilitado por padrão), alterar o limite de tempo ocioso e decidir se os usuários podem ou não fazer chamadas telefônicas enquanto estiverem bloqueados ou usando as configurações inband. Consulte [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) para obter mais detalhes sobre essas configurações.
    
## <a name="step-7-optional---if-you-have-device-pairing-and-better-together-over-ethernet-btoe"></a>Etapa 7 (opcional) - Se você tiver emparelhamento de dispositivo e Better Together over Ethernet (BToE)
<a name="BK_BTOE"> </a>

O BToE é um mecanismo de emparelhamento para telefones IP de parceiros que emparelha o telefone do usuário com o aplicativo do Skype for Business para Windows. Ele habilita os usuários a:
  
- Entrar no telefone IP usando o aplicativo Skype for Business para área de trabalho (usando um PC)
    
- Sincronizar o bloqueio de telefone com o bloqueio de PC
    
- Clicar para telefonar
    
O BToE pode ser configurado para operar em 2 modos;  *Automático* (padrão) e *Manual*. Ele também pode ser habilitado (padrão) ou desabilitado para usuários com configurações inband do Skype for Business. Ao operar no modo *Manual*, os usuários precisam executar um passo adicional para emparelhar o telefone com o aplicativo do Windows.
  
 **Para implantar o BToE para os usuários**
  
1. Conecte o PC deles ao telefone usando a porta do PC.
    
     ![Implementar telefones.](../../images/e21d76c7-867c-4fe6-95c6-fc40c608ed0c.png)
  
2. Baixe e instale o software BToE mais recente do site do fabricante usando os links abaixo. Para uma melhor experiência do usuário, você pode distribuir e instalar o software BToE usando uma solução de distribuição de administração como o SCCM (System Center Configuration Manager). Para obter ajudar sobre como usar o SCCM, consulte [Pacotes e programas no System Center Configuration Manager](https://docs.microsoft.com/en-us/sccm/apps/deploy-use/packages-and-programs).
    
  - [Site para download do software BToE Polycom](http://www.polycom.com/voice-conferencing-solutions/microsoft-phones.html)
    
  - [Download de software BToE Yealink](http://www.yealink.com/products_list_10.html)
    
  - [Downloads de software BToE AudioCodes](https://www.audiocodes.com/solutions-products/solutions/skype-for-business-microsoft-teams/skype-for-business-online)
    
3. Por padrão, a configuração de servidor para BToE é definida como **Ativado** e **Modo automático**. Para alterar essas configurações, consulte [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx).
    
> [!NOTE]
> O BToE não é permitido atualmente nas plataformas Mac e VDI. 
  
## <a name="related-topics"></a>Tópicos relacionados
[Obter números de telefone de serviço do Skype for Business e do Microsoft Teams](../../what-is-phone-system-in-office-365/getting-service-phone-numbers.md)

[Veja aqui o que é fornecido com o Sistema de Telefonia no Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[Disponibilidade da Audioconferência e dos Planos de Chamadas por país e região](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
 
