---
title: Implantar o Portal da Web Administrativo do SRS v1 no Skype for Business Server
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
ms.assetid: 81822efa-2100-4017-a470-8a5b98c49522
ms.collection: M365-voice
description: O Portal da Web Administrativo do Skype for Business Server Skype Room Systems v1 (SRS v1, anteriormente conhecido como Sistema de Salas do Lync) é um portal da Web que as organizações podem usar para manter suas salas de conferência do Skype Room Systems. Os administradores podem usar o Portal da Web Administrativo do SRS v1 para monitorar a saúde do dispositivo, por exemplo, monitorando dispositivos de áudio/vídeo. Com esse portal, os administradores podem coletar remotamente informações de diagnóstico para monitorar a saúde da sala de conferência.
ms.openlocfilehash: 7d7bef99149d09ebf72c9b633370f262e535b23f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804531"
---
# <a name="deploy-srs-v1-administrative-web-portal-in-skype-for-business-server"></a>Implantar o Portal da Web Administrativo do SRS v1 no Skype for Business Server

O Portal da Web Administrativo do Skype for Business Server Skype Room Systems v1 (SRS v1, anteriormente conhecido como Sistema de Salas do Lync) é um portal da Web que as organizações podem usar para manter suas salas de conferência do Skype Room Systems. Os administradores podem usar o Portal da Web Administrativo do SRS v1 para monitorar a saúde do dispositivo, por exemplo, monitorando dispositivos de áudio/vídeo. Com esse portal, os administradores podem coletar remotamente informações de diagnóstico para monitorar a saúde da sala de conferência.

Para usar esse recurso, o Portal da Web Administrativo do SRS v1 precisa ser implantado em cada Servidor Front-End do Skype for Business Server. Este guia fornece instruções para os administradores sobre como instalar e configurar o Portal da Web Administrativo do SRS. Destina-se a administradores que têm conhecimento da administração do Skype for Business Server e que têm direitos de usuário de administrador para modificar a topologia do Skype for Business Server.

Depois que o Portal da Web Administrativo do SRS v1 é implantado no servidor, os administradores podem verificar o status dos dispositivos SRS v1 fazendo logo login no site em seus próprios computadores ou laptops.

> [!IMPORTANT]
> Baixe o Portal da Web Administrativo [do Microsoft Skype Room Systems v1 para Skype for Business Server 2015.](https://www.microsoft.com/download/details.aspx?id=46906)

Neste tópico:

- [Configurar seu ambiente para o Portal da Web Administrativo do SRS v1](room-system-v1-administrative-web-portal.md#Config_Env)

- [Instalar o Portal da Web Administrativo do SRS v1](room-system-v1-administrative-web-portal.md#Install_SRS)

- [Usar o Portal da Web Administrativo do SRS](room-system-v1-administrative-web-portal.md#Use_Portal)

## <a name="configure-your-environment-for-the-srs-v1-administrative-web-portal"></a>Configurar seu ambiente para o Portal da Web Administrativo do SRS v1
<a name="Config_Env"> </a>

Para usar o Portal da Web Administrativo do SRS v1, você precisará instalar ou configurar os seguintes pré-requisitos.

> [!IMPORTANT]
> Se o servidor estiver configurado com autenticação Kerberos e NTLM e o SRS estiver em execução em um computador que não ingressou no domínio, a autenticação Kerberos falhará e o usuário não verá o status do SRS no portal administrativo. Para resolver esse problema, configure o servidor com autenticação NTLM ou autenticação NTLM e TLS-DSK (sem Kerberos) ou insinue o computador SRS no domínio.

1. Instale as Atualizações Cumulativas do Skype for Business Server na topologia do Skype for Business Server.

    Para obter a atualização ou ver o que está incluído nele, consulte Atualizações para [o Skype for Business Server 2015.](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)

2. Crie um usuário do Active Directory habilitado para SIP.

    O Portal da Web Administrativo do SRS v1 usa essas credenciais para consultar informações do Skype for Business Server. O nome de usuário nos exemplos determinados é LRSApp.

3. Crie um grupo de segurança do Active Directory com o nome LRSSupportAdminGroup.

    Crie o grupo com Escopo de Grupo como Global e Tipo de Grupo como Segurança. Os usuários habilitados para SIP que são adicionados a esse grupo serão autorizados a ver a lista de salas e executar determinados comandos, como coletar logs.

4. Crie um grupo de segurança do Active Directory com o nome LRSFullAccessAdminGroup.

    Crie o grupo com Escopo de Grupo como Global e Tipo de Grupo como Security.SIP. Os usuários habilitados para SIP adicionados a esse grupo estão autorizados a usar toda a funcionalidade do portal de administração em uma única sala do Skype. Para incluir suporte para gerenciamento em massa de salas do Skype, consulte a etapa 5.

     ![Lista de grupos de administração com a função de grupo de segurança](../../media/LRS_LRSFullAccessAdminGroup.png)

5. Crie um grupo de segurança do Active Directory com o nome LRSPowerUserAdminsGroup.

    Crie o grupo com Escopo de Grupo como Global e Tipo de Grupo como Segurança. Os usuários habilitados para SIP adicionados a esse grupo estão autorizados a usar toda a funcionalidade do portal de administração, incluindo o gerenciamento em massa de salas do Skype for Business.

6. Adicione LRSFullAccessAdminGroup como membro do LRSSupportAdminGroup.

     ![Página Membros das Propriedades LRSSupportAdminGroup](../../media/LRS_Add_LRSSupportAdminGroup.png)

7. Crie um usuário do Active Directory habilitado para SIP com o nome LRSSupport. Adicione esse usuário a LRSSupportAdminGroup.

     ![Página Membros das Propriedades LRSSupportAdminGroup](../../media/LRS_Add_LRS_SIP_SupportUser.png)

8. Instale [ASP.NET MVC 4 para Visual Studio 2010 SP1 e Visual Web Developer 2010 SP1.](https://go.microsoft.com/fwlink/p/?LinkId=323967)

## <a name="install-the-srs-v1-administrative-web-portal"></a>Instalar o Portal da Web Administrativo do SRS v1
<a name="Install_SRS"> </a>

Baixe o Portal da Web Administrativo [do Microsoft Skype Room Systems v1 para Skype for Business Server 2015.](https://www.microsoft.com/download/details.aspx?id=46906)

Para instalar o Portal da Web Administrativo do SRS v1, use as etapas a seguir.

1. Configure a Porta de Aplicativo Confiável executando o seguinte cmdlet no Shell de Gerenciamento do Skype for Business Server:

   ```powershell
   Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457
   ```

2. Para instalar o Portal de Sala de Reunião, baixe **MeetingRoomPortalInstaller.msi** e execute-o como administrador.

3. Abra o Web.config arquivo no seguinte local:

    %Program Files%\Skype for Business Server 2015\Web Components\Meeting Room Portal\Int\Handler\

4. No arquivo Web.Config, altere PortalUserName para o nome de usuário criado na Etapa 2, na seção " Configurar seu ambiente para o Portal da Web Administrativo do[SRS v1](room-system-v1-administrative-web-portal.md#Config_Env)" (o nome recomendado na etapa é LRSApp):

    ```xml
    <add key="PortalUserName" value="sip:LRSApp@domain.com" />
    ```

5. Como o Portal de Administração do SRS v1 é um aplicativo confiável, você não precisa fornecer a senha na configuração do portal. Se esse usuário estiver usando um registrador diferente do registrador local, você precisará especificar o registrador para ele adicionando a seguinte linha no arquivo de Web.Config:

   ```xml
   <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />
   ```

6. Se a porta usada for diferente de 5061, adicione a seguinte linha no Web.Config arquivo:

   ```xml
   <add key="PortalUserRegistrarPort" value="5061" />
   ```

### <a name="verify-installation-of-the-srs-administrative-web-portal"></a>Verificar a instalação do Portal da Web Administrativo do SRS

Para verificar a instalação do Portal da Web Administrativo do SRS v1, faça o seguinte:

1. Em um servidor front-end, navegue até a seguinte URL:

    https:// \<fe-server\> /lrs

    Você não deve ver erros, conforme mostrado na imagem a seguir:

     ![Lync Room System Admin Portal Sign In screen](../../media/LRS_AdminPortalSignIn.png)

2. Se você não vir erros, tente acessar a SEGUINTE URL de qualquer outro computador na topologia:

    https:// \<fe-server\> /lrs

    Para acessar a página, você precisará adicionar os registros DNS conforme descrito em " Registros DNS necessários para entrada automática do[cliente".](https://go.microsoft.com/fwlink/p/?LinkId=318056)

## <a name="use-the-srs-administrative-web-portal"></a>Usar o Portal da Web Administrativo do SRS
<a name="Use_Portal"> </a>

Depois de implantar o SRS no servidor, você pode verificar o status de todas as salas do SRS entrando no Portal da Web Administrativo do SRS v1 a partir de um navegador.

### <a name="sign-in"></a>Entrar

1. Navegue até a seguinte URL:

    https:// \<fe-server\> /lrs

2. Insira as credenciais da conta LRSSupport ou de uma conta que foi adicionada ao grupo de segurança LRSSupportAdminGroup.

![Lync Room System Admin Portal Sign In screen](../../media/LRS_AdminPortalSignIn.png)

### <a name="srs-administrative-web-portal-summary-page"></a>Página de Resumo do Portal da Web Administrativo do SRS

A página de resumo fornece as seguintes informações para todas as salas do SRS implantadas no servidor:

- **Tag** O nome personalizado que o administrador fornece à sala. A marca pode ser definida no portal clicando no nome da sala.

- **Health** O status de saúde da sala, que é derivado do status de Saúde Agregada da sala, que é mostrado na seção De saúde da página Configurações da Sala.

- **Próxima Reunião** A data e a hora em que a próxima reunião está agendada.

- **Versão do SRS, Fabricante, Modelo** Esses valores são predefinidos no SRS. Dependendo do fabricante, esses campos podem ser deixados em branco.

- **Última atualização** Exibe a última vez que a página da Web foi atualizada.

![Lync Room System Admin Portal Summary View](../../media/LRS_AdminPortal_Summary_view.png)

> [!NOTE]
> Você só verá o menu Gerenciamento em Massa se for parte do grupo de segurança LRSPowerUserAdminsGroup.

### <a name="srs-room-information"></a>Informações da Sala SRS

A seção Informações da Sala do portal permite que você veja e configure salas SRS individuais. Ele contém quatro seções: Configurações, Detalhes, Log e Saúde.

#### <a name="settings"></a>Configurações

Na seção Configurações, você pode definir a senha, a marca da sala e os níveis de volume padrão da sala. Se você definir essas configurações, as alterações serão replicadas somente depois que você reiniciar o console do SRS. Você só verá as configurações de Atualizações do Sistema para dispositivos SRS usando a versão 15.12 e posterior.

![Configurações da sala do Portal de Administração do Sistema de Sala do Lync](../../media/LRS_AdminPortal_RoomInfoSettings.png)

#### <a name="details"></a>Detalhes

A seção Detalhes fornece um resumo somente leitura das configurações da sala SRS, incluindo: a hora da última atualização; próxima reunião; últimas atualizações, manutenção e calibragem; configurações padrão de alto-falante, microfone e toque; versão; URI do SIP; número de telas e detalhes sobre cada tela; status e atividade.

![Lync Room System Admin Portal Detail View](../../media/LRS_AdminPortal_Detail_view.png)

#### <a name="troubleshooting"></a>Solução de problemas

A seção Solução de Problemas pode ser usada remotamente para coletar logs e salvá-los em um local especificado. Você também pode reiniciar o console do SRS (interface do usuário do SRS) ou reiniciar todo o sistema. Para coletar logs, forneça um caminho de pasta no formato especificado e certifique-se de que a pasta tenha permissões de gravação concedidas à conta da máquina do SRS. Se o tamanho do log for muito grande, pode levar até 5 minutos para concluir a coleta de logs. Atualizar a página lhe dará o status mais recente.

#### <a name="health"></a>Integridade

A seção Health fornece uma indicação visual da saúde da conexão do Skype for Business Server, do dispositivo de áudio, do dispositivo de vídeo, do estado de resiliência e do dispositivo de tela.

![Lync Room System Admin Portal Room Health](../../media/LRS_AdminPortal_RoomInfoHealth.png)

### <a name="additional-notes-about-the-administrative-web-portal"></a>Observações adicionais sobre o Portal da Web Administrativo

> [!NOTE]
>  As alterações de configuração são aplicadas somente depois que o sistema SRS é reiniciado.> Se a senha da conta LRSApp expirar, você não poderá ver o status das salas. Configure a senha da conta LRSAppuser para que ela nunca expire ou atualize a senha quando estiver próximo de expirar.> O portal da Web administrativo do SRS é suportado apenas para implantações locais.

### <a name="bulk-management"></a>Gerenciamento em massa

O gerenciamento em massa de salas SRS é um recurso projetado para administradores avançados de IT, para simplificar seu fluxo de trabalho e habilita-los com uma ferramenta conveniente de economia de tempo para gerenciar remotamente várias salas em massa.

Para ver essa funcionalidade, o usuário precisa ser provisionado como membro do grupo de segurança especial, **LRSPowerUserAdminsGroup**.

Não há limite para o número de salas do SRS que você pode selecionar para gerenciamento em massa. No entanto, você pode executar apenas uma operação de gerenciamento em massa por vez.

Para executar uma operação de gerenciamento em massa, selecione as salas que deseja monitorar e clique no menu Gerenciamento em massa.

### <a name="frequently-asked-questions"></a>Perguntas frequentes

#### <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a>Por que não consigo entrar no portal da Web administrativo?

Ao abrir, você poderá ver a página de login, mas quando digitar suas credenciais, não https://localhost/lrs poderá entrar. Nesse caso, você deve abrir https://FQDNofFEserver/SRS para entrar no portal da Web administrativo.

#### <a name="why-cant-i-see-srs-v1-in-the-administrative-web-portal"></a>Por que não consigo ver o SRS v1 no portal da Web administrativo?

- Certifique-se de que você tenha contas do SRS em sua implantação e que elas sejam criadas de acordo com as recomendações de implantação do Portal da Web Administrativo do SRS. Certifique-se de que as contas do SRS sejam provisionadas usando Enable-CsMeetingRoom, não Enable-CsUser, no Skype for Business Server.

- Se você criou contas do SRS e não pode ver as contas no portal da Web administrativo, colete os logs do servidor usando a ferramenta Log do Skype for Business Server com o componente **MeetingPortal** selecionado e envie-os para o contato de suporte do SRS.

- Se você criou contas do SRS e não pode ver as contas no portal da Web administrativo, colete os logs do cliente usando o Fiddler e copie o log do console das ferramentas de desenvolvimento do navegador e envie-as para o contato de suporte do SRS. Você também pode modificar o valor do nível de rastreamento no Web.config obter um log mais detalhado.

  ```xml
  <system.diagnostics>
    <switches>
      <!--
      This switch controls logging message levels. 0 implies
      logging is turned off. 1 implies only errors are logged,
      2 implies errors &amp; warnings. 4 is the most detailed.
      -->
      <add name="TraceLevelSwitch" value="3" />
    </switches>
  </system.diagnostics>
  ```

#### <a name="why-cant-i-see-the-status-of-srs-in-the-administrative-web-portal"></a>Por que não consigo ver o status do SRS no portal da Web administrativo?

- Certifique-se de que a conta de usuário LRSApp seja habilitada para SIP.

- Se você ainda estiver com problemas, colete o arquivo **Trace.log** no sistema SRS de D:\Tracing\LRSAdminLogs e envie-o para o contato de suporte \, do SRS.

#### <a name="why-cant-i-see-the-bulk-management-menus-for-srs-in-the-administrative-web-portal"></a>Por que não consigo ver os menus de gerenciamento em massa do SRS no portal da Web administrativo?

Certifique-se de que a conta de usuário LRSApp seja habilitada para SIP e faça parte do grupo de segurança LRSPowerUserAdminsGroup.

#### <a name="does-the-srs-v1-administrative-web-portal-work-with-microsoft-teams-rooms"></a>O portal da Web administrativo do SRS v1 funciona com as Salas do Microsoft Teams?

Não.


