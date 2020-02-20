---
title: Solicitar e configurar um certificado para seu proxy HTTP reverso
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Request and configure a certificate for your reverse HTTP proxy
ms:assetid: 4b70991e-5f10-40a3-b069-0b227c3a3a0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429704(v=OCS.15)
ms:contentKeyID: 48184085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c380cb67e1e156bef616f81ce0c42f699b472d8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144938"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="request-and-configure-a-certificate-for-your-reverse-http-proxy-in-lync-server-2013"></a>Solicitar e configurar um certificado para seu proxy HTTP reverso no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-02-14_

Você precisa instalar o certificado de autoridade de certificação (CA) raiz no servidor que executa o Microsoft Forefront Threat Management Gateway 2010 ou IIS ARR para a infraestrutura de CA que emitiu os certificados do servidor para os servidores internos que executam o Microsoft Lync Server 2013.

Você também deve instalar um certificado de servidor web público no seu servidor proxy reverso. Os nomes alternativos de entidade desse certificado devem conter os FQDNs (nomes de domínio totalmente qualificados) externos publicados de cada pool que é o início para usuários habilitados para acesso remoto, e os FQDNs externos de todos os Diretores ou pools de Diretores que serão usados dentro dessa infraestrutura de Borda. O nome alternativo da entidade também deve conter a URL simples de reunião, a URL simples de discagem e, se você estiver implantando aplicativos móveis e planejar usar descoberta automática, a URL do Serviço Descoberta Automática externo, como mostrado na tabela a seguir.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Valor</th>
<th>Exemplo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Nome da entidade</p></td>
<td><p>FQDN do pool</p></td>
<td><p>webext.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>Nome alternativo da entidade</p></td>
<td><p>FQDN do pool</p></td>
<td><p>webext.contoso.com</p>



> [!IMPORTANT]
> O nome da entidade também deve estar presente no nome alternativo da entidade.

</td>
</tr>
<tr class="odd">
<td><p>Nome alternativo da entidade</p></td>
<td><p>Serviços Web de diretor opcional (se o diretor estiver implantado)</p></td>
<td><p>webdirext.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>Nome alternativo da entidade</p></td>
<td><p>URL simples de reunião</p>



> [!NOTE]
> Todas as URLs simples de reunião devem estar no nome alternativo da região. Cada domínio SIP deve ter pelo menos uma URL simples de reunião ativa.

</td>
<td><p>meet.contoso.com</p></td>
</tr>
<tr class="odd">
<td><p>Nome alternativo da entidade</p></td>
<td><p>URL simples de discagem</p></td>
<td><p>dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>Nome alternativo da entidade</p></td>
<td><p>Servidor do Office Web Apps</p></td>
<td><p>officewebapps01.contoso.com</p></td>
</tr>
<tr class="odd">
<td><p>Nome alternativo da entidade</p></td>
<td><p>URL de Serviço Descoberta Automática Externo</p></td>
<td><p>lyncdiscover.contoso.com</p>



> [!NOTE]
> Se você estiver usando o Microsoft Exchange Server, você também precisará configurar regras de proxy reverso para as URLs de descoberta automática e serviços Web do Exchange.

</td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]
> Se sua implantação interna consiste em mais de um servidor Standard Edition ou pool de Front-End, você deve configurar regras de publicação na Web para cada FQDN de web farm externo e será necessário um ouvinte da web e certificado para cada um, ou você deve obter um certificado cujo nome alternativo da entidade contém os nomes usados por todos os pools, atribuí-lo a um ouvinte da web e compartilhá-lo entre várias regras de publicação na web.



</div>

<div>

## <a name="create-a-certificate-request"></a>Criar uma solicitação de certificado

Você cria uma solicitação de certificado no proxy reverso. Você cria uma solicitação em outro computador, mas deve exportar o certificado assinado com a chave privada e importá-lo para o proxy reverso depois de ter recebido a autoridade de certificação pública.

<div>


> [!NOTE]
> Uma solicitação de certificado ou uma solicitação de assinatura de certificado (CSR) é uma solicitação para uma autoridade de certificação pública (AC) confiável para validar e assinar a chave pública do computador solicitante. Quando um certificado é gerado, uma chave pública e uma chave privada são criadas. Somente a chave pública é compartilhada e assinada. Como o nome indica, a chave pública é disponibilizada para qualquer solicitação Pública. A chave pública é usada por clientes, servidores e outros solicitantes que precisam trocar informações com segurança e validar a identidade de um computador. A chave privada é mantida protegida e é usada apenas pelo computador que criou o par de chaves para descriptografar mensagens criptografadas com sua chave pública. A chave privada pode ser usada para outros fins. Para fins de proxy reverso, a criptografia de dados é o uso principal. Secondarily, a autenticação de certificado no nível de chave do certificado é outra, e é limitada somente à validação de que um solicitante tem a chave pública do computador ou que o computador para o qual você tem uma chave pública é realmente o computador que ele alega ser.



</div>

<div>


> [!TIP]
> Se você planejar os certificados do servidor de borda e os certificados de proxy reverso ao mesmo tempo, observe que há uma grande semelhança entre os dois requisitos de certificado. Ao configurar e solicitar seu certificado de servidor de borda, combine o servidor de borda e os nomes alternativos de entidade de proxy reverso. Você pode usar o mesmo certificado para seu proxy reverso se exportar o certificado e a chave privada e copiar o arquivo exportado para o proxy reverso e, em seguida, importar o par de certificados/chaves e atribuí-lo conforme necessário nos próximos procedimentos. Consulte os requisitos de certificado para o plano do&nbsp;servidor<A href="lync-server-2013-plan-for-edge-server-certificates.md">de borda para certificados de servidor de borda no Lync Server 2013</A> e o resumo de certificado de proxy reverso <A href="lync-server-2013-certificate-summary-reverse-proxy.md">-proxy reverso no Lync Server 2013</A>. Certifique-se de criar o certificado com uma chave privada exportável. A criação da solicitação de certificado e certificado com uma chave privada exportável é necessária para servidores de borda em pool, portanto, esta é uma prática normal e o assistente de certificado no assistente de implantação do Lync Server para o servidor de borda permitirá que você defina o sinalizador de <STRONG>exportação de chave privada</STRONG> . Quando receber a solicitação de certificado de volta da autoridade de certificação pública, você exportará o certificado e a chave privada. Consulte a seção "para exportar o certificado com a chave privada para servidores de borda em um pool" no tópico <A href="lync-server-2013-set-up-certificates-for-the-external-edge-interface.md">configurar certificados para a interface de borda externa do Lync Server 2013</A> para obter detalhes sobre como criar e exportar o certificado com uma chave privada. A extensão do certificado deve ser do tipo <STRONG>. pfx</STRONG>.



</div>

Para gerar uma solicitação de assinatura de certificado no computador onde o certificado e a chave privada serão atribuídos, faça o seguinte:

**Criar uma solicitação de assinatura de certificado**

1.  Abra o console de gerenciamento Microsoft (MMC) e adicione o snap-in certificados e selecione **computadores**e, em seguida, expanda **pessoal**. Para obter detalhes sobre como criar um console de certificados no MMC (console de gerenciamento Microsoft), [https://go.microsoft.com/fwlink/?LinkId=282616](https://go.microsoft.com/fwlink/?linkid=282616)consulte.

2.  Clique com o botão direito do mouse em **certificados**, clique em **todas as tarefas**, em **operações avançadas**, em **criar solicitação personalizada**.

3.  Na página **registro de certificado** , clique em **Avançar**.

4.  Na página **selecionar política de registro de certificado** em **solicitação personalizada**, selecione **continuar sem política de registro**. Clique em **Avançar**.

5.  Na página **solicitação personalizada** , em **modelo** selecionar **(sem modelo) chave herdada**. Salvo indicação em contrário pelo provedor de certificados, deixe **suprimir as extensões padrão** desmarcadas e a seleção de **formato de solicitação** no **PKCS \#10**. Clique em **Avançar**.

6.  Na página **informações do certificado** , clique em **detalhes**e, em seguida, clique em **Propriedades**.

7.  Na página de **Propriedades do certificado** , na guia **geral** , no campo **nome amigável** , digite um nome para esse certificado. Opcionalmente, digite uma descrição no campo **Descrição** . O nome amigável e a descrição normalmente são usados pelo administrador para identificar qual é a finalidade do certificado, como o **ouvinte de proxy reverso para o Lync Server**.

8.  Selecione a guia **assunto** . Em **nome do assunto** para o **tipo**, selecione **nome comum** para o tipo de nome de entidade. Para o **valor**, digite o nome da entidade que você usará para o proxy reverso e clique em **Adicionar**. No exemplo fornecido na tabela deste tópico, o nome da entidade é webext.contoso.com e deve ser digitado no campo value para o nome do assunto.

9.  Na guia **assunto** em **nome alternativo**, selecione **DNS** na lista suspensa para **tipo**. Para cada nome alternativo de entidade definido que você precisa no certificado, digite o nome de domínio totalmente qualificado e clique em **Adicionar**. Por exemplo, na tabela há três nomes alternativos da entidade, meet.contoso.com, dialin.contoso.com e lyncdiscover.contoso.com. No campo **valor** , digite Meet.contoso.com e clique em **Adicionar**. Repita o procedimento para cada nome alternativo de entidade que você precisa definir.

10. Na página de **Propriedades do certificado** , clique na guia **extensões** . Nesta página, você definirá os objetivos da chave criptográfica no **uso da chave** e o uso estendido da chave no **uso estendido de chave (políticas de aplicativo)**.

11. Clique na seta **uso da chave** para mostrar as **opções disponíveis**. Em opções disponíveis, clique em **assinatura digital**e, em seguida, clique em **Adicionar**. Clique em **codificação de chave**e, em seguida, clique em **Adicionar**. Se a caixa de seleção **tornar esses usos de chave críticos** estiver desmarcada, marque a caixa de seleção.

12. Clique na seta **uso estendido da chave (políticas de aplicativo)** para mostrar as **opções disponíveis**. Em opções disponíveis, clique em **autenticação do servidor**e, em seguida, clique em **Adicionar**. Clique em **autenticação do cliente**e, em seguida, clique em **Adicionar**. Se a caixa de seleção para **tornar crítico os usos estendidos de chave** for marcada, desmarque a caixa de seleção. Ao contrário da caixa de seleção uso da chave (que deve ser marcada), você deve ter certeza de que a caixa de seleção uso estendido de chave não está marcada.

13. Na página de **Propriedades do certificado** , clique na guia **chave privada** . Clique na seta **Opções de teclas** . Em **tamanho da chave**, selecione **2048** na lista suspensa. Se você estiver gerando esse par de chaves e o CSR em um computador diferente do proxy reverso para o qual esse certificado se destina, selecione **tornar a chave privada exportável**.
    
    <div>
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398321.security(OCS.15).gif" title="segurança" alt="security" />Observação de segurança:</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Selecionar <strong>tornar uma chave privada exportável</strong> é geralmente avisado quando você tem mais de um proxy reverso em um farm, pois você copiará o certificado e a chave privada para cada computador no farm. Se você permitir uma chave privada exportável, deverá ter cuidado adicional com o certificado e o computador em que ele é gerado. A chave privada, se comprometida, tornará o certificado inútil, bem como exporá potencialmente o computador ou os computadores para acesso externo e outras vulnerabilidades de segurança.</td>
    </tr>
    </tbody>
    </table>
    
    </div>

14. Na guia **chave privada** , clique na seta **tipo de chave** . Selecione a opção **Exchange** .

15. Clique em **OK** para salvar as **Propriedades de certificado** que você definiu.

16. Na página **registro de certificado** , clique em **Avançar**.

17. Na página **onde você deseja salvar a solicitação offline?** , você será solicitado a fornecer um **nome de arquivo** e um formato de **arquivo** para salvar a solicitação de assinatura de certificado.

18. No campo de entrada **nome do arquivo** , digite um caminho e um nome de arquivo para a solicitação ou clique em **procurar** para selecionar um local para o arquivo e digite o nome do arquivo para a solicitação.

19. Em **formato de arquivo**, clique em **base 64** ou **binário**. Selecione **Base 64** , a menos que você tenha instruído de outra forma pelo fornecedor de seus certificados.

20. Localize o arquivo de solicitação que você salvou na etapa anterior. Envie para sua autoridade de certificação pública.
    
    <div>
    

    > [!IMPORTANT]
    > A Microsoft identificou autoridades de certificação públicas que atendem aos requisitos para fins de comunicação unificada. Uma lista é mantida no seguinte artigo da base de dados de conhecimento. <A href="https://go.microsoft.com/fwlink/?linkid=282625">https://go.microsoft.com/fwlink/?LinkId=282625</A>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

