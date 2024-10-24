# Guava

## Composite Recipes

_Recipes that include further recipes, often including the individual recipes below._

* [Prefer `Integer#compareUnsigned`](./preferintegercompareunsigned.md)
* [Prefer `Integer#divideUnsigned`](./preferintegerdivideunsigned.md)
* [Prefer `Long#compareUnsigned`](./preferlongcompareunsigned.md)
* [Prefer `Long#divideUnsigned`](./preferlongdivideunsigned.md)
* [Prefer `Math#addExact`](./prefermathaddexact.md)
* [Prefer `Math#clamp`](./prefermathclamp.md)
* [Prefer `Math#multiplyExact`](./prefermathmultiplyexact.md)
* [Prefer `Math#subtractExact`](./prefermathsubtractexact.md)
* [Prefer `java.util.Objects#equals`](./preferjavautilobjectsequals.md)
* [Prefer `java.util.Objects#hash`](./preferjavautilobjectshashcode.md)
* [Prefer `java.util.Objects#requireNonNullElse`](./preferjavautilobjectsrequirenonnullelse.md)
* [Prefer `java.util.Optional`](./preferjavautiloptional.md)
* [Prefer `java.util.function.Predicate`](./preferjavautilpredicate.md)
* [Prefer the Java 11 standard library instead of Guava](./noguavajava11.md)
* [Prefer the Java 21 standard library instead of Guava](./noguavajava21.md)
* [Prefer the Java standard library instead of Guava](./noguava.md)
* [Refaster style Guava to Java migration recipes](./noguavarefasterrecipes.md)

## Recipes

* [`Preconditions.checkNotNull` to `Objects.requireNonNull`](./noguavarefasterrecipes$preconditionschecknotnulltoobjectsrequirenonnullrecipe.md)
* [`Preconditions.checkNotNull` with `Object` message to `Objects.requireNonNull` with `String.valueOf`](./noguavarefasterrecipes$preconditionschecknotnullwithmessagetoobjectsrequirenonnullmessagetypeobjectrecipe.md)
* [`Preconditions.checkNotNull` with `String` message to `Objects.requireNonNull`](./noguavarefasterrecipes$preconditionschecknotnullwithmessagetoobjectsrequirenonnullrecipe.md)
* [Prefer `Arrays.asList(..)` over Guava primitives](./noguavaprimitiveaslist.md)
* [Prefer `Files#createTempDirectory()`](./noguavacreatetempdir.md)
* [Prefer `Integer#compare`](./preferintegercompare.md)
* [Prefer `Integer#parseUnsignedInt`](./preferintegerparseunsignedint.md)
* [Prefer `Integer#remainderUnsigned`](./preferintegerremainderunsigned.md)
* [Prefer `List.of(..)` in Java 9 or higher](./noguavaimmutablelistof.md)
* [Prefer `Long#compare`](./preferlongcompare.md)
* [Prefer `Long#parseUnsignedInt`](./preferlongparseunsignedlong.md)
* [Prefer `Long#remainderUnsigned`](./preferlongremainderunsigned.md)
* [Prefer `Map.of(..)` in Java 9 or higher](./noguavaimmutablemapof.md)
* [Prefer `Runnable::run`](./noguavadirectexecutor.md)
* [Prefer `Set.of(..)` in Java 9 or higher](./noguavaimmutablesetof.md)
* [Prefer `Short#compare`](./prefershortcompare.md)
* [Prefer `String#join()` over Guava `Joiner#join()`](./preferjavastringjoin.md)
* [Prefer `java.lang.Char#compare`](./prefercharcompare.md)
* [Prefer `java.nio.charset.StandardCharsets`](./preferjavaniocharsetstandardcharsets.md)
* [Prefer `java.util.Collections#synchronizedNavigableMap`](./preferjavautilcollectionssynchronizednavigablemap.md)
* [Prefer `java.util.Collections#unmodifiableNavigableMap`](./preferjavautilcollectionsunmodifiablenavigablemap.md)
* [Prefer `java.util.Optional#or(Supplier<T extends java.util.Optional<T>>)`](./preferjavautiloptionalorsupplier.md)
* [Prefer `java.util.Optional#orElse(null)` over `com.google.common.base.Optional#orNull()`](./preferjavautiloptionalorelsenull.md)
* [Prefer `java.util.function.Function`](./preferjavautilfunction.md)
* [Prefer `java.util.function.Supplier`](./preferjavautilsupplier.md)
* [Prefer `new ArrayList<>()`](./noguavalistsnewarraylist.md)
* [Prefer `new AtomicReference<>()`](./noguavaatomicsnewreference.md)
* [Prefer `new ConcurrentHashMap<>()`](./noguavasetsnewconcurrenthashset.md)
* [Prefer `new CopyOnWriteArrayList<>()`](./noguavalistsnewcopyonwritearraylist.md)
* [Prefer `new HashMap<>()`](./noguavamapsnewhashmap.md)
* [Prefer `new HashSet<>()`](./noguavasetsnewhashset.md)
* [Prefer `new LinkedHashMap<>()`](./noguavamapsnewlinkedhashmap.md)
* [Prefer `new LinkedHashSet<>()`](./noguavasetsnewlinkedhashset.md)
* [Prefer `new LinkedList<>()`](./noguavalistsnewlinkedlist.md)
* [Prefer `new TreeMap<>()`](./noguavamapsnewtreemap.md)
* [Remove `com.google.common.base.Optional#toJavaUtil()`](./noguavaoptionaltojavautil.md)
* [Replace `com.google.common.base.Optional#fromJavaUtil(java.util.Optional)` with argument](./noguavaoptionalfromjavautil.md)

