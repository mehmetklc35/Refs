Refs & Portals
** Advanced DOM Access & Value Management

->>> Accessing DOM Elements with Refs
->>> Managing Values With Refs
->>> Exposing API Functions from Components
->>> Detaching DOM Rendering form JSX Structure with Portals

->> Bu proje Refs Kullanım Özellikleri geliştirmek amacıyla yapılmıştır...

**** DOM elemanlarına erişim elde etmek için Refs özelliğini nasıl kullanabiliriz...
**** State olmaması gereken değerleri yönetmek için Refs özelliğini nasıl kullanabiliriz...
**** Bir API yi açığa çıkaran Bileşenleri nasıl oluşturabiliriz....
**** Portalların ne olduğun ve DOM'da işlendiği yeri JSX kodumuzda kullandığımız yerden ayırmak için 
        Portallar özelliğini nasıl kullanabiliriz....

***************************************************************************************************************
When writing JSX code, there's one important rule: A JSX value must have only one root element.

For example, the following code would be invalid and cause an error:

return (
  <h2>Welcome!</h2>
  <p>React is awesome!</p>
);
So would this code:

const content = (
  <h2>Welcome!</h2>
  <p>React is awesome!</p>
);
In both snippets, the JSX value has two sibling root elements - and that's not allowed!

One solution would be to wrap these elements into a <div> - which then acts as a single root JSX element:

return (
  <div>
    <h2>Welcome!</h2>
    <p>React is awesome!</p>
  </div>
);
This would work and therefore is an acceptable solution.

But it has a downside: You now have that extra <div> in your DOM - even though you don't really need it (besides for getting rid of the this error).

That's why React offers a better solution: A special JSX element called "React Fragment".

It can be used as a wrapper to ensure that there's only one root JSX element whilst at the same time not rendering any DOM element.

You can use it like this:

import { Fragment } from 'react';
 
// ... other code ...
 
return (
  <Fragment>
    <h2>Welcome!</h2>
    <p>React is awesome!</p>
  </Fragment>
);
Most React projects (e.g., projects created with Vite or create-react-app) offer an even shorter form:

// no import needed
 
return (
  <>
    <h2>Welcome!</h2>
    <p>React is awesome!</p>
  </>
);
***********************************************************************************************************
JSX kodu yazarken önemli bir kural vardır: Bir JSX değerinin yalnızca bir kök öğesi olmalıdır.

Örneğin, aşağıdaki kod geçersiz olur ve bir hataya neden olur:

return (
<h2>Hoş geldiniz!</h2>
<p>React harika!</p>
Bu kod da öyle:

const content = (
<h2>Hoş geldiniz!</h2>
<p>React harika!</p>
Her iki kod parçacığında da JSX değeri iki kardeş kök öğeye sahiptir - ve bu izin verilmez!

Bir çözüm, bu öğeleri bir <div> içine sarmak olabilir - bu daha sonra tek bir kök JSX öğesi gibi davranır:

return (
<div>
<h2>Hoş geldiniz!</h2>
<p>React harika!</p>
</div>
Bu işe yarar ve bu nedenle kabul edilebilir bir çözümdür.

Ancak bir dezavantajı vardır: Artık DOM'unuzda o fazladan <div> öğesi var - buna gerçekten ihtiyacınız olmasa bile (bu hatadan kurtulmak dışında).

Bu nedenle React daha iyi bir çözüm sunar: "React Fragment" adlı özel bir JSX öğesi.

Herhangi bir DOM öğesini işlemeden yalnızca bir kök JSX öğesi olduğundan emin olmak için bir sarmalayıcı olarak kullanılabilir.

Bunu şu şekilde kullanabilirsiniz:

import { Fragment } from 'react';

// ... diğer kod ...

return (
<Fragment>
<h2>Hoş geldiniz!</h2>
<p>React harika!</p>
</Fragment>
Çoğu React projesi (örneğin, Vite veya create-react-app ile oluşturulan projeler) daha da kısa bir biçim sunar:

// içe aktarma gerekmez

return (
<>
<h2>Hoş geldiniz!</h2>
<p>React harika!</p>
</>
);

