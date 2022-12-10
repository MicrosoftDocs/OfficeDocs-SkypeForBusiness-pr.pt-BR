---
title: Configurar o Gateway SIP
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 12/8/2022
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: Saiba como configurar o GATEWAY SIP.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: c93aec7cb65cdd40c05a540b51a3da8ba268c7e9
ms.sourcegitcommit: feb9b7d10e38f5a629ee9202b5aaec5beef4de9b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2022
ms.locfileid: "69343273"
---
# <a name="configure-sip-gateway"></a>Configurar o Gateway SIP

Este artigo explica como configurar o Sip Gateway para que sua organização possa usar dispositivos SIP compatíveis com Microsoft Teams. Para descobrir o que o SIP Gateway pode fazer para sua organização e quais hardware, software e licenças sua organização precisa para ele, leia [Planejar para o Sip Gateway](sip-gateway-plan.md).

Antes de configurar o SIP Gateway, faça o seguinte:

- **Redefinir dispositivos SIP para configurações padrão de fábrica.** Você ou os usuários da sua organização devem redefinir cada dispositivo SIP usado com o SIP Gateway para suas configurações padrão de fábrica. Para descobrir como fazer isso, consulte as instruções do fabricante.

- **Abra o firewall para Microsoft 365 e Teams.** Abra o firewall da rede para Microsoft tráfego do 365 e do Teams, conforme descrito em [URLs Office 365 e intervalos de endereços IP](/microsoft-365/enterprise/urls-and-ip-address-ranges). Regras de firewall são necessárias apenas para tráfego de saída.

- **Verifique se os dispositivos SIP não estão atrás de um proxy.** Verifique se o tráfego http/s ignora qualquer proxy de http/s corporativo.

- **Abra a porta UDP.** Abra a porta UDP no intervalo 49152 a 53247 para intervalos de IP 52.112.0.0.0/14 e 52.122.0.0/15.

- **Abra a porta TCP.** Abra a porta TCP 5061 para intervalos de IP 52.112.0.0/14 e 52.122.0.0/15.

- **Abra os seguintes pontos de extremidade https (endereços IP e URLs):**

  - 13.75.175.145
  - 52.189.219.201
  - 51.124.34.164
  - 13.74.250.91
  - 13.83.55.36
  - 23.96.103.40
  - https://blobsdgapac.blob.core.windows.net
  - https://blobsdgemea.blob.core.windows.net
  - https://blobsdgnoam.blob.core.windows.net
  - https://httpblobsdgapac.blob.core.windows.net
  - https://httpblobsdgemea.blob.core.windows.net
  - https://httpblobsdgnoam.blob.core.windows.net


As seções a seguir descrevem o que você deve fazer como administrador para configurar o GATEWAY SIP.

- [Verifique se o Gateway SIP está disponível para sua organização](#verify-that-sip-gateway-is-available-for-your-organization).

- [Habilite o GATEWAY SIP para os usuários da sua organização](#enable-sip-gateway-for-the-users-in-your-organization).

- [Defina a URL do servidor de provisionamento do SIP Gateway](#set-the-sip-gateway-provisioning-server-url).

Este artigo também descreve como:

- [Registre dispositivos SIP individualmente ou em lotes para sua conveniência](#provision-and-enroll-sip-devices-as-common-area-phones).  

- [Exiba e monitore seus dispositivos SIP.](#view-and-monitor-sip-devices)

- [Habilite o suporte para uma interface do usuário de vários idiomas.](#set-a-sip-devices-ui-language)

## <a name="verify-that-sip-gateway-is-available-for-your-organization"></a>Verifique se o GATEWAY SIP está disponível para sua organização

1. Entre no [centro de administração do Teams](https://admin.teams.microsoft.com/).

2. À esquerda, selecione **Dispositivos do Teams** e veja se a guia **dispositivos SIP** está visível. Se for, o serviço SIP Gateway estará habilitado para sua organização.

## <a name="enable-sip-gateway-for-the-users-in-your-organization"></a>Habilitar o SIP Gateway para os usuários em sua organização

Você pode habilitar o SIP Gateway para sua organização de duas maneiras: usando o centro de administração do Teams ou usando um cmdlet do PowerShell.

### <a name="by-using-teams-admin-center"></a>Usando o centro de administração do Teams

Para habilitar o GATEWAY SIP no centro de administração do Teams, siga estas etapas:

1. Vá para o [centro de administração do Teams](https://admin.teams.microsoft.com/)

2. À esquerda, em **Voz**, selecione **Políticas de chamada**.

3. À direita, em **Gerenciar políticas**, selecione a política de chamada apropriada atribuída aos usuários ou, se necessário, crie uma nova política de chamada e atribua-a aos usuários necessários.

4. Selecione **Gerenciar políticas**, selecione uma política e selecione **Editar**.

5. Ative a configuração para **dispositivos SIP pode ser usada para chamadas** e selecione **Salvar**.


### <a name="by-using-powershell"></a>Usando o PowerShell

Você também pode habilitar o GATEWAY SIP usando o cmdlet [PowerShell Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy) . Para habilitar os usuários para dispositivos SIP, selecione uma política e defina o `-AllowSIPDevicesCalling` atributo como `True`. O valor padrão é `False`, portanto, os usuários não poderão usar seus dispositivos SIP, a menos que você os habilite.

> [!NOTE]
> - A propagação da política pode levar até 24 horas.

## <a name="set-the-sip-gateway-provisioning-server-url"></a>Definir a URL do servidor de provisionamento do SIP Gateway

Você pode definir a URL do servidor de provisionamento do SIP Gateway no servidor DHCP (Protocolo de Configuração do Host Dinâmico). Os usuários que trabalham remotamente devem configurá-lo manualmente.

### <a name="using-dhcp"></a>Usando DHCP

Para cada dispositivo SIP, defina uma das seguintes URLs de servidor de provisionamento do SIP Gateway: 

- EMEA: `http://emea.ipp.sdg.teams.microsoft.com`
- Américas: `http://noam.ipp.sdg.teams.microsoft.com`
- APAC: `http://apac.ipp.sdg.teams.microsoft.com`

Adicione dispositivos SIP à sua organização teams configurando a URL do servidor de provisionamento do SIP Gateway acima no servidor DHCP. Para saber mais sobre o servidor DHCP, consulte [Implantar e gerenciar o DHCP](/training/modules/deploy-manage-dynamic-host-configuration-protocol). Além disso, você pode usar a opção DHCP 42 para especificar o servidor NTP (Protocolo de Tempo de Rede) e a opção DHCP 2 para especificar o deslocamento do UTC (Tempo Universal Coordenado) em segundos. Os dispositivos em sua organização serão roteados para o servidor de provisionamento do SIP Gateway. Os telefones SIP provisionados com êxito exibirão o logotipo do Teams e um botão macio para entrada.

Verifique se os dispositivos SIP estão na versão de firmware com suporte mínimo para integração. Durante a integração, o Gateway SIP enviará push da interface do usuário de configuração e autenticação padrão para o dispositivo. Para descobrir a versão de firmware necessária para dispositivos SIP, consulte [Planejar o Gateway SIP](sip-gateway-plan.md).

### <a name="manually"></a>Manualmente

Os usuários que trabalham remotamente devem configurar manualmente a URL do servidor de provisionamento em seu dispositivo SIP usando as seguintes etapas:

1. Abra **Configurações** no dispositivo e obtenha o endereço IP do dispositivo.

2. Abra uma janela do navegador, insira o endereço IP do dispositivo, faça logon (se necessário) e configure a URL do servidor de provisionamento no utilitário Web do dispositivo.

3. Em **Configurações** ou **Configurações avançadas** no utilitário Web, insira a URL do servidor de provisionamento mostrada acima.

> [!NOTE]
> - Somente dispositivos SIP compatíveis podem ser integrados ao GATEWAY SIP. 
> - Os telefones IP cisco devem ser exibidos para firmware multiplataforma antes que possam ser integrados. Para saber como, consulte [Guia de conversão de firmware da Cisco](https://www.cisco.com/c/en/us/products/collateral/collaboration-endpoints/unified-ip-phone-7800-series/guide-c07-742786.html).
> - Para telefones Yealink, use a opção 66.
> - Para telefones Cisco, Poly e AudioCode, use a opção 160. 
> - Para dispositivos Cisco, anexe **/$PSN.xml** à URL do servidor de provisionamento.


## <a name="configure-conditional-access"></a>Configurar o acesso condicional

O Acesso Condicional é um recurso do Azure Active Directory (Azure AD) que ajuda a garantir que os dispositivos que acessam seus recursos Microsoft 365 sejam gerenciados e seguros corretamente. O GATEWAY SIP autentica dispositivos SIP com Azure AD, portanto, se sua organização usa o Acesso Condicional para dispositivos na rede corporativa, ele deve excluir os seguintes endereços IP:

- América do Norte:
    - Leste dos EUA: 52.170.38.140
    - Oeste dos EUA: 40.112.144.212
-   Região EMEA:
    - Norte da UE: 40.112.71.149
    - Oeste da UE: 40.113.112.67
-   Região do APAC:
    - Leste da Austrália: 20.92.120.71
    - Sudeste da Austrália: 13.73.115.90

Para obter mais informações, confira [Intervalos de endereços IP](/azure/active-directory/conditional-access/location-condition#ip-address-ranges).

## <a name="provision-and-enroll-sip-devices-as-common-area-phones"></a>Provisionar e registrar dispositivos SIP como telefones de área comum

> [!NOTE]
> Um dispositivo SIP deve ser integrado ao Gateway SIP antes de poder ser registrado.

Para simplificar suas tarefas, você pode registrar dispositivos SIP no centro de administração do Teams, um de cada vez ou em lotes. Veja como:

1. Faça logon no [**centro de administração do Teams**](https://admin.teams.microsoft.com).

2. Selecione **Dispositivos DO Teams DISPOSITIVOS** > **SIP**.

3. No canto superior direito, selecione **Dispositivos de Provisionamento** de **Ações** >  e siga uma destas etapas:

  - **Para provisionar um dispositivo:**

     a. Em **Aguardando ativação**, selecione **Adicionar**.

     b. No painel **Adicionar endereços MAC, insira** o **endereço MAC** e o **Local** do dispositivo e selecione **Aplicar**.
     
     c. Em **Aguardando ativação**, selecione o dispositivo que você acabou de adicionar e selecione **Gerar código de verificação**.
     
     d. No painel **Provisionar dispositivos** , em **Código de verificação**, observe o código de verificação do dispositivo SIP.

   - **Para provisionar muitos dispositivos:**

     a. Em **Aguardando ativação**, à direita, selecione **Exportar** (o ícone Microsoft Excel).
     
     b. No painel **Provisionar dispositivos** , em **Carregar vários endereços MAC**, selecione **baixar um modelo**.
     
     c. Salve **Template_Provisioning.csv** no computador e preencha os campos **ID** mac e **Localização** .
    
     d. No painel **Provisionar dispositivos** , selecione **Carregar vários endereços MAC**. 

     e. À direita, no painel **Carregar endereços MAC** , **selecione Selecionar um arquivo** e selecione o arquivo **Template_Provisioning.csv** que contém seus dados.

     F. No painel **Provisionar dispositivos** , **em Aguardando ativação**, selecione um dispositivo e selecione **Gerar código de verificação** para gerar um código de verificação único para cada dispositivo provisionado. Observe o código de verificação de cada dispositivo SIP.

4. No dispositivo SIP, disce o código do recurso de registro seguido pelo código de verificação. No dispositivo SIP, disce o código \*do recurso de registro 55* (usado pelo SIP Gateway para validação de código de verificação única de registro), seguido pelo código de verificação gerado no Teams Administração Center para este dispositivo específico. Por exemplo, se o código de verificação for 123456, disque \*55\*123456 para registrar o dispositivo.

5.  No painel **Provisionar dispositivos** , **em Aguardando entrada**, selecione **Sair**.

6. Na caixa de diálogo **Entrar em um usuário** , copie ou observe o código de emparelhamento do dispositivo SIP.

7. Vá para [https://microsoft.com/devicelogin](https://microsoft.com/devicelogin), e em **Inserir código**, insira o código de emparelhamento do dispositivo SIP e selecione **Avançar**.

8. Na página **Entrar** Microsoft, no campo **Email ou telefone**, insira o endereço de email do dispositivo SIP e selecione **Avançar**.

9. Na página **Senha** , insira a senha do endereço de email do dispositivo SIP e selecione **Entrar**.

10. Na página **De entrada no gateway de dispositivos SIP do Teams** , selecione **Continuar**.

## <a name="how-to-sign-in-and-sign-out"></a>Como entrar e sair

Há suporte apenas para entrada local para dispositivos pessoais dos usuários. Para assinar um dispositivo no centro de Administração, siga estas etapas:

1. Faça logon no [**centro de administração do Teams**](https://admin.teams.microsoft.com).

2. Selecione **Dispositivos DO Teams DISPOSITIVOS** > **SIP**.

3. À direita, selecione um dispositivo SIP e selecione **Sair**.


### <a name="user-pairing-and-sign-in"></a>Emparelhamento e entrada do usuário

Para emparelhar um dispositivo SIP após a autenticação do usuário usando credenciais corporativas, um usuário deve:

1. Pressione **Entrar** no telefone SIP para exibir a URL de autenticação e o código de emparelhamento. O código de emparelhamento é sensível ao tempo. Se expirar, o usuário deverá pressionar **Novamente** o telefone e iniciar o processo de entrada novamente.

2. Navegue até a URL de autenticação na área de trabalho ou no navegador móvel do usuário e use credenciais corporativas para fazer logon.

3. Insira o código de emparelhamento exibido no telefone SIP no aplicativo de autenticação web para emparelhar o telefone SIP com a conta do usuário. Em uma entrada bem-sucedida, o que pode demorar um pouco, o telefone SIP exibirá o número de telefone e o nome de usuário, se o dispositivo der suporte a ele.

> [!NOTE]
> O local do dispositivo mostrado no aplicativo de autenticação Web do Azure Active Directory é o datacenter do GATEWAY SIP ao qual o dispositivo está conectado. Os telefones SIP no escopo não são capazes de OAuth, portanto, o GATEWAY SIP autentica o usuário por meio do aplicativo de autenticação web e emparelha o dispositivo com as credenciais do usuário. Saiba mais aqui: [plataforma de identidade da Microsoft e o fluxo de concessão de autorização do dispositivo OAuth 2.0](/azure/active-directory/develop/v2-oauth2-device-code).

### <a name="sign-out"></a>Saída

Para sair, um usuário do dispositivo pode:

- Pressione **Sair** no dispositivo SIP e siga as etapas descritas no dispositivo. 

Para assinar um dispositivo no centro de administração do Teams:

1. Faça logon no [**centro de administração do Teams**](https://admin.teams.microsoft.com).

2. Selecione **Dispositivos DO Teams DISPOSITIVOS** > **SIP**.

3. À direita, no painel **dispositivos SIP** , selecione o dispositivo.

4. No painel Detalhes do dispositivo, **selecione** a guia **Detalhes** e, na parte superior direita, no menu **Ações** , selecione **Sair**. 

## <a name="view-and-monitor-sip-devices"></a>Exibir e monitorar dispositivos SIP

Você pode exibir e monitorar seu inventário de dispositivo SIP no centro de administração do Teams depois que os usuários dos dispositivos entrarem pelo menos uma vez. Veja como:

1. Faça logon no [centro de administração do Teams](https://admin.teams.microsoft.com/).

2. Selecione **Dispositivos DO Teams DISPOSITIVOS** > **SIP**. Todos os dispositivos SIP conectados estão listados à direita.

## <a name="restart-a-sip-device"></a>Reiniciar um dispositivo SIP

1. Faça logon no [centro de administração do Teams](https://admin.teams.microsoft.com).

2. Selecione **Dispositivos DO Teams DISPOSITIVOS** > **SIP**. 

3. À direita, selecione o dispositivo SIP que você deseja reiniciar e **selecione Reiniciar**.


> [!NOTE]
> - Atualmente, a remoção de um dispositivo SIP do locatário não está disponível no centro de administração do Teams. 
> - A execução de comando depende da disponibilidade do dispositivo e pode não corresponder ao status de execução mostrado no centro de administração do Teams. Se você tentar habilitar o gateway SIP em um dispositivo que não dá suporte a ele, o comando não será executado.

## <a name="sync-policy-changes-to-sip-devices-to-enforce-policies"></a>Sincronizar alterações de política em dispositivos SIP para impor políticas

Os detalhes e as políticas do usuário serão buscados nos dispositivos SIP quando os usuários entrarem. Qualquer alteração de política posteriormente para usuários conectados será sincronizada com o dispositivo dentro de uma hora. Os dispositivos devem ter seu registro atualizado com o Gateway SIP periodicamente. Os telefones SIP dependem do Redirecionamento de Chamadas, portanto, o administrador deve definir o `AllowCallRedirect` atributo como `Enabled``Set-CsTeamsCallingPolicy` .


## <a name="set-a-sip-devices-ui-language"></a>Definir a linguagem de interface do usuário de um dispositivo SIP

Um dispositivo SIP geralmente pode exibir informações em muitos idiomas. A configuração de sua linguagem de interface do usuário afeta sua interface, incluindo teclas softkeys e mensagens do sistema de entrada/saída. Definir o idioma da interface do usuário é feito no servidor de provisionamento, usando o servidor DHCP ou acrescentando manualmente uma cadeia de caracteres de código na URL como nos exemplos a seguir.

Como definir o alemão para telefones Polycom, AudioCodes e Yealink:
- `http://emea.ipp.sdg.teams.microsoft.com/lang_de`

Como definir o japonês para telefones Cisco:
- `http://emea.ipp.sdg.teams.microsoft.com/lang_ja/$PSN.xml` 


### <a name="supported-languages"></a>Idiomas com suporte

|Nome da linguagem|Código de linguagem]
|-------------|-------------|
|Inglês (padrão)|En       |
|Espanhol      |Es           |
|Japonês     |ja           |
|Alemão       |de           |
|Francês       |Fr           |
|Português   |pt           |

> [!Note]
> - O japonês não tem suporte do Yealink e tem suporte parcial do Polycom VVX.
> - O sistema será padrão para o inglês se o idioma selecionado não tiver suporte pelo ponto de extremidade SIP.
> - Quando o parâmetro **lang_xx** não é definido por meio da URL de provisionamento, o inglês é usado como o idioma padrão.
> - Se **Entrar para fazer um texto de chamada de emergência** não for traduzido para outros idiomas, uma versão abreviada em inglês só será apresentada no **Press Sign In** nos seguintes modelos de telefone IP devido a limitações de tela:
>   - Poly VVX 150, VVX 201
>   - Cisco CP-6821, CP-7811, CP-7821, CP-7841, CP-7861
>   - O rótulo softkey de email de voz é codificado com texto **de VM** em todos os idiomas para Poly VVX devido a uma limitação do comprimento da cadeia de caracteres.

## <a name="microsoft-teams-and-ipv6"></a>Microsoft Teams e IPv6

O Gateway SIP dá suporte apenas ao IPv4. Microsoft suporte ao cliente e ao serviço do Teams tanto IPv4 quanto IPv6. Se você quiser controlar as comunicações para Microsoft Teams, use os intervalos de endereços IP em [Microsoft 365 URLs e intervalos de endereços IP](/microsoft-365/enterprise/urls-and-ip-address-ranges).

## <a name="emergency-calling"></a>Chamada de emergência

O GATEWAY SIP dá suporte à chamada de emergência dinâmica (E911 dinâmica) para dispositivos SIP compatíveis que compartilham atributos de rede pelo fio. Esses atributos são provisionados no centro de administração do Teams e podem ser uma combinação de IP local e comprimento de sub-rede, ou ID do chassi e número da porta de rede. Para dispositivos que não compartilham atributos de localização ou se o local não for resolvido dinamicamente por qualquer motivo, o GATEWAY SIP continuará a dar suporte a chamadas de emergência com base em endereços registrados. Atualmente, não há suporte para endereços registrados para cenários de Roteamento Direto. Para obter mais informações sobre chamadas de emergência, consulte [Planejar e gerenciar chamadas de emergência](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing).

## <a name="report-problems-to-microsoft"></a>Relatar problemas ao Microsoft

Para relatar problemas, entre em contato [com Suporte da Microsoft](https://support.microsoft.com).
