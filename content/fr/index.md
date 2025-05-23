---
title: Preact
---

<jumbotron>
    <h1>
        <logo height="1.5em" title="Preact" text="true" inverted="true">Preact</logo>
    </h1>
    <p class="tagline">Alternative légère et rapide à React avec le même API en seulement 3Ko</p>
    <p class="intro-buttons">
        <a href="/guide/v10/getting-started" class="btn primary">Commencer</a>
        <a href="/guide/v10/switching-to-preact" class="btn secondary">Passer à preact</a>
    </p>
</jumbotron>

```jsx
function Counter() {
  const [value, setValue] = useState(0);

  return (
    <>
      <div>Counter: {value}</div>
      <button onClick={() => setValue(value + 1)}>Increment</button>
      <button onClick={() => setValue(value - 1)}>Decrement</button>
    </>
  )
}
```

<div class="sponsors">
  <p><a href="https://opencollective.com/preact">Sponsorisé par:</a></p>
  <sponsors></sponsors>
</div>

<section class="home-top">
    <h2>Un concept différent</h2>
</section>


<section class="home-section">
  <img src="/home/metal.svg" alt="metal" loading="lazy" decoding="async" width="54" height="54">

  <div>
    <h3>Plus proche de la machine</h3>
    <p>
        Preact possède l'abstraction du DOM virtuel la plus fine.
        Le web est une plateforme stable, il est temps d'arrêter de réinventer la roue.
    </p>
    <p>
        Preact est aussi au premier rang de la plateforme web. Il compare le DOM virtuel avec le DOM du navigateur, enregistre de vrais gestionnaires d'événements et fonctionne très bien avec les autres bibliothèques.
    </p>
  </div>
</section>


<section class="home-section">
  <img src="/home/size.svg" alt="size" loading="lazy" decoding="async" width="54" height="54">

  <div>
    <h3>Petite taille</h3>
    <p>
        La plupart des frameworks UI sont très larges et possèdent généralement plus de code que votre application. Preact est différent : la majorité du code de votre application sera le vôtre.
    </p>
    <p>
        Concrètement, moins de code Javascript sera à télécharger, à analyser et à exécuter. De ce fait, votre code sera privilégié.
    </p>
  </div>
</section>


<section class="home-section">
  <img src="/home/performance.svg" alt="performance" loading="lazy" decoding="async" width="54" height="54">

  <div>
    <h3>Grande performance</h3>
    <p>
        Preact est performant, non seulement à cause de sa taille, mais aussi parce qu'il possède une des implémentations les plus rapides pour détecter les différences entre le DOM du navigateur et le DOM virtuel.
    </p>
    <p>
        Il implémente certaines fonctionnalités supplémentaires à React telles que <a href="/guide/configuration#debounceRendering">les updates en batch</a>, <a href="/guide/configuration#syncComponentUpdates">les mises à jour asynchrones</a> et la réutilisation du DOM.
    </p>
  </div>
</section>


<section class="home-section">
  <img src="/home/portable.svg" alt="portable" loading="lazy" decoding="async" width="54" height="54">

  <div>
    <h3>Portable &amp; embarquable</h3>
    <p>
        Contrairement aux autres frameworks, Preact ne représente pas un énorme surcoût. Il vous permettra de bénéficier de la puissance du DOM virtuel.
    </p>
    <p>
        Vous pouvez utiliser Preact pour bâtir une partie de votre application sans difficultés d'intégration. Ajouter Preact à un widget se fait de la même façon que vous construiriez une application complète.
    </p>
  </div>
</section>


<section class="home-section">
  <img src="/home/productive.svg" alt="productive" loading="lazy" decoding="async" width="54" height="54">

  <div>
    <h3>Productif instantanément</h3>
    <p>
        La légèreté est plus amusante quand vous n'avez pas à sacrifier la productivité pour y arriver. Avec Preact vous serez productif en quelques instants. Vous aurez même droit aux fonctionnalités supplémentaires suivantes :
    </p>
    <ul>
        <li>Les `props`, `state` et `context` sont passés en arguments de la méthode `render()`</li>
        <li>Les attributs standards HTML comme `class` et `for` peuvent être utilisés</li>
    </ul>
  </div>
</section>


<section class="home-section">
  <div>
    <img src="/home/compatible.svg" alt="compatible" loading="lazy" decoding="async" width="54" height="54">
    <h3>Compatible avec l'écosystème</h3>
    <p>
        Les composants du DOM virtuel vous permettent de réutiliser des briques de votre application. Grâce à la conception de Preact, vous avez à votre disposition les composants de l'écosystème React.
    </p>
    <p>
        Un simple alias vers <a href="/guide/v10/switching-to-preact#how-to-alias-preact-compat">preact-compat</a> apporte une couche de compatibilité qui permet l'utilisation des fonctionnalités les plus complexes de React.
    </p>
  </div>
</section>


<section class="home-top">
    <h2>Voir en action!</h2>
</section>


<section class="home-split">
    <div>
        <h3>Composant liste de tâches</h3>
        <pre><code class="language-jsx">
// --repl
export default class TodoList extends Component {
    state = { todos: [], text: '' };
    setText = e =&gt; {
        this.setState({ text: e.currentTarget.value });
    };
    addTodo = () =&gt; {
        let { todos, text } = this.state;
        todos = todos.concat({ text });
        this.setState({ todos, text: '' });
    };
    render({ }, { todos, text }) {
        return (
            &lt;form onSubmit={this.addTodo} action="javascript:"&gt;
                &lt;label&gt;
                  &lt;span&gt;Add Todo&lt;/span&gt;
                  &lt;input value={text} onInput={this.setText} /&gt;
                &lt;/label&gt;
                &lt;button type="submit"&gt;Add&lt;/button&gt;
                &lt;ul&gt;
                    { todos.map( todo =&gt; (
                        &lt;li&gt;{todo.text}&lt;/li&gt;
                    )) }
                &lt;/ul&gt;
            &lt;/form&gt;
        );
    }
}
// --repl-after
render(&lt;TodoList /&gt;, document.getElementById("app"));
        </code></pre>
    </div>
    <div>
        <h3>Exemple interactif</h3>
        <pre repl="false"><code class="language-jsx">
import TodoList from './todo-list';<br>
render(&lt;TodoList /&gt;, document.body);
        </code></pre>
        <div class="home-demo">
            <todo-list></todo-list>
        </div>
    </div>
</section>


<section class="home-split">
    <div>
        <h3>Récupérer les Stars Github</h3>
        <pre><code class="language-jsx">
// --repl
export default class Stars extends Component {
    async componentDidMount() {
        let stars = await githubStars(this.props.repo);
        this.setState({ stars });
    }
    render({ repo }, { stars=0 }) {
        let url = `https://github.com/${repo}`;
        return (
            &lt;a href={url} class="stars"&gt;
                ⭐️ {stars} Stars
            &lt;/a&gt;
        );
    }
}
// --repl-after
render(&lt;Stars repo="preactjs/preact" /&gt;, document.getElementById("app"));
        </code></pre>
    </div>
    <div>
        <h3>Exemple fonctionnel</h3>
        <pre repl="false"><code class="language-jsx">
import Stars from './stars';<br>
render(
    &lt;Stars repo="developit/preact" /&gt;,
    document.body
);
        </code></pre>
        <div class="home-demo">
            <github-stars simple="true" user="preactjs" repo="preact"></github-stars>
        </div>
    </div>
</section>


<section class="home-top">
    <h2>Prêt à vous lancer ?</h2>
</section>


<section style="text-align:center;">
    <p>
        Nous avons séparé les guides en fonction de votre expérience avec React.
        <br>
        Choisissez celui qui vous convient.
    </p>
    <p>
        <a href="/guide/v10/getting-started" class="btn primary">Commencer</a>
        <a href="/guide/v10/switching-to-preact" class="btn secondary">Passer à Preact</a>
    </p>
</section>
