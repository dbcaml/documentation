---
sidebar_position: 1
---


This is the documentation for version v0.0.1. This documentation will be updated 

Basic Example usage:

```ocaml {filename="main.ml"}

let driver =
  Dbcaml_driver_postgres.connection
    "postgresql://postgres:mysecretpassword@localhost:6432/development"
in

let pool_id = Dbcaml.start_link ~connections:10 driver |> Result.get_ok in

(* Fetch 1 row from the database *)
(match
   Dbcaml.fetch_one
     pool_id
     ~params:[Dbcaml.Param.String "1"]
     "select * from users where id = $1"
 with
| Ok x ->
  let rows = Dbcaml.Row.row_to_type x in
  (* Iterate over each column and print its values *)
  List.iter (fun x -> print_endline x) rows
| Error x -> print_endline (Dbcaml.Res.execution_error_to_string x));

```
