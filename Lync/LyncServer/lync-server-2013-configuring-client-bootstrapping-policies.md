---
title: 'Lync Server 2013: Configurando políticas de inicialização do cliente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring client bootstrapping policies
ms:assetid: 45042eca-b845-4207-b12f-b8b7f5d44bdf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425941(v=OCS.15)
ms:contentKeyID: 48184031
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 457702a4b237493beb8ca5dfe1e2d7ce9b3d2654
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135528"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-client-bootstrapping-policies-in-lync-server-2013"></a>Configurando políticas de inicialização do cliente no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-21_

O GPMC (console de gerenciamento de política de grupo) e o editor de objeto de diretiva de grupo são ferramentas que você usa para gerenciar a política de grupo. Incluído no modelo administrativo da política de grupo do Office estão os modelos administrativos do Lync 2013. admx (ADMX) e. adml (ADML), que contêm as configurações de política baseadas no registro que você configura para os objetos de política de grupo no domínio. Os arquivos ADML são complementos específicos do idioma para arquivos ADMX. Cada arquivo ADMX e ADML contém as configurações de política para um único aplicativo do Office. Para obter mais informações, consulte "arquivos de modelo administrativo do Office 2013 (ADMX, ADML)" na documentação do <https://go.microsoft.com/fwlink/p/?linkid=267516>Office 2013 em.

Para o Lync 2013, há várias políticas de inicialização do cliente que devem ser consideradas configuradas antes que os usuários entrem no servidor pela primeira vez. Por exemplo, os servidores e o modo de segurança padrão que o cliente deve usar até que o logon seja concluído. Você pode usar a política de grupo para estabelecer essas configurações nos registros de computador dos usuários antes de entrar e começar a receber as configurações de provisionamento em banda no servidor. A tabela a seguir lista as configurações de política de grupo disponíveis para o Lync 2013.

### <a name="group-policy-settings-for-lync-2013"></a>Configurações da política de grupo para o Lync 2013

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Configuração da Política de grupo</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Especificar servidor<br />
ConfigurationMode</p></td>
<td><p>Especifica como o Lync 2013 identifica o transporte e o servidor a serem usados durante a entrada. Nesta configuração, especifique o seguinte:</p>
<ul>
<li><p>ServerAddressExternal: especifica o nome do servidor ou endereço IP usado por clientes e contatos federados ao se conectar de fora do firewall externo.</p></li>
<li><p>ServerAddressInternal: especifica o nome do servidor ou endereço IP usado quando os clientes se conectam de dentro do firewall da organização.</p></li>
<li><p>Transport: especifica o protocolo de controle de transmissão (TCP) ou TLS (Transport Layer Security).</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Versões de servidor adicionais suportadas<br />
(ConfiguredServerCheckValues)</p></td>
<td><p>Especifica uma lista de nomes de versão de servidor separados por ponto e vírgula nos quais o Lync Server 2013 fará logon, além das versões de servidor que têm suporte por padrão.</p></td>
</tr>
<tr class="odd">
<td><p>Desabilitar o carregamento automático de logs de falha de entrada (DisableAutomaticSendTracing)</p></td>
<td><p>Carrega automaticamente os logs de falha de entrada no Lync Server para análise. Nenhum log será carregado automaticamente se a conexão for bem-sucedida. Se essa política não estiver configurada, ocorrerá o seguinte:</p>
<dl>
<dt><span></span></dt>
<dd><p>Para usuários do Lync Online: logs de falha de entrada são carregados automaticamente.</p>
</dd>
<dt><span></span></dt>
<dd><p>Para usuários locais do Lync: uma caixa de diálogo de confirmação é exibida para o usuário antes do carregamento.</p>
</dd>
</dl>
<p>Quando essa configuração é desabilitada, os logs de entrada são carregados automaticamente no Lync Server para os usuários do Lync local e do Lync Online. Quando essa configuração é habilitada, os logs de entrada nunca são carregados automaticamente.</p></td>
</tr>
<tr class="even">
<td><p>Desabilitar fallback de HTTP para conexão SIP<br />
(DisableHttpConnect)</p></td>
<td><p>Impede que o Lync Server tente se conectar ao servidor usando HTTP, se TLS ou TCP não estiverem disponíveis. Por padrão, o Lync primeiro tenta se conectar ao servidor usando TLS ou TCP e, se nenhum desses métodos de transporte for bem-sucedido, o Lync tentará se conectar usando HTTP. Use essa política para desabilitar a tentativa de conexão HTTP de fallback.</p></td>
</tr>
<tr class="odd">
<td><p>Exigir credenciais de logon<br />
DisableNTCredentials</p></td>
<td><p>Requer que o usuário forneça credenciais de logon para o Lync em vez de usar automaticamente as credenciais do Windows durante a entrada em um servidor SIP.</p></td>
</tr>
<tr class="even">
<td><p>Desabilitar verificação de versão do servidor<br />
(DisableServerCheck)</p></td>
<td><p>Se você definir essa política como 1, o Lync não poderá verificar o nome e a versão do servidor antes de entrar. Por padrão, o Lync faz essas verificações antes de entrar.</p></td>
</tr>
<tr class="odd">
<td><p>Habilitar o uso de BITS para baixar arquivos do serviço de catálogo de endereços<br />
(EnableBitsForGalDownload)</p></td>
<td><p>Permite que o Lync use o serviço de transferência inteligente em segundo plano (BITS) para baixar os arquivos dos serviços de catálogo de endereços.</p></td>
</tr>
<tr class="even">
<td><p>Configurar o modo de segurança SIP<br />
(EnableSIPHighSecurityMode)</p></td>
<td><p>Permite que o Lync envie e receba mensagens instantâneas com mais segurança. Essa política não tem efeito sobre os serviços .NET ou Microsoft Exchange Server do Windows.</p>
<p>Se você não definir essa configuração de política, o Lync poderá usar qualquer transporte. Mas se ele não usar TLS e se o servidor autenticar usuários, o Lync deverá usar a autenticação NTLM ou Kerberos.</p></td>
</tr>
<tr class="odd">
<td><p>Atraso inicial de download do catálogo de endereços global<br />
(GalDownloadInitialDelay)</p></td>
<td><p>Especifica o período de tempo antes da ocorrência de um download da GAL (lista de endereços global). O valor padrão é 60 minutos, o que significa que o servidor atrasa o download do arquivo GAL por um período aleatório entre 0 e 60 minutos.</p></td>
</tr>
<tr class="even">
<td><p>Impedir que os usuários executem o Microsoft Lync<br />
(PreventRun)</p></td>
<td><p>Impede que os usuários executem o Lync. Você pode configurar essa definição de diretiva em Configuração do Computador e em Configuração do Usuário, mas a definição de Configuração do Computador tem precedência.</p></td>
</tr>
<tr class="odd">
<td><p>Permitir o armazenamento de senhas de usuário<br />
SavePassword</p></td>
<td><p>Permite que o Lync armazene senhas.</p></td>
</tr>
<tr class="even">
<td><p>Configurar o modo de compactação SIP<br />
(SipCompression)</p></td>
<td><p>Especifica quando ativar a compactação SIP. Por padrão, a compactação SIP é ativada com base na velocidade do adaptador. Observe que a configuração dessa política pode causar um aumento no tempo de login.</p></td>
</tr>
<tr class="odd">
<td><p>Lista de domínios confiáveis<br />
TrustModelData</p></td>
<td><p>Lista os domínios confiáveis que não correspondem ao prefixo do domínio SIP do cliente.</p></td>
</tr>
</tbody>
</table>


As políticas configuradas no servidor têm precedência sobre as configurações de Política de Grupo e as opções de cliente configuradas pelo usuário. A tabela a seguir resume a ordem na qual as configurações têm precedência quando ocorre um conflito.

### <a name="group-policy-precedence"></a>Precedência das Políticas de Grupo

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Precedence</th>
<th>Local ou método da configuração</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p>Provisionamento em banda do Lync Server 2013</p></td>
</tr>
<tr class="even">
<td><p>duas</p></td>
<td><p>HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\Office\15.0\Lync</p></td>
</tr>
<tr class="odd">
<td><p>3D</p></td>
<td><p>HKEY_CURRENT_USER \SOFTWARE\Policies\Microsoft\Office\15.0\Lync</p></td>
</tr>
<tr class="even">
<td><p>quatro</p></td>
<td><p>A caixa de diálogo Lync-Options no Lync 2013</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-define-group-policy-settings-by-using-the-lync-2013-administrative-template-files"></a>Para definir as configurações de política de grupo usando os arquivos de modelo administrativo do Lync 2013

1.  Crie uma pasta de nível de raiz para que contenha todos os arquivos ADMX de idioma neutro. Por exemplo, crie a pasta raiz do repositório central em seu controlador de domínio neste local:
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    
    <div>
    

    > [!NOTE]  
    > Este procedimento pressupõe que você deseja gerenciar vários computadores em seu domínio. Nesse caso, você armazena os modelos em um repositório central na pasta SYSVOL no controlador de domínio primário. Isso oferece um local de repositório central para Modelos Administrativos do domínio.

    
    </div>

2.  Crie uma subpasta para cada idioma que você usará. Essas subpastas conterão os arquivos de recurso ADML específicos do idioma. Por exemplo, crie uma subpasta para o inglês dos Estados Unidos (EN-US) neste local:
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`

</div>

</div>

<span> </span>

</div>

</div>

</div>

